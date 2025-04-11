# Project Phase 2 - Basic Structure and Main Functionalities

**Project link on GitHub**: [ecommerce-project](https://github.com/Celia0322/ecommerce-project/tree/main)

## 1. Environment

The development environment for this project is designed to support both the frontend and backend using modern web technologies and tools.

### Backend:
- **Node.js**: The backend is built using Node.js, which provides the runtime environment for the server-side JavaScript code.
- **Express**: Express.js is used as the backend framework to handle HTTP requests, routes, and middleware.
- **MongoDB (via MongoDB Atlas)**: MongoDB is used as the database for storing product information, user data, and orders. It is connected using Mongoose, an ODM (Object Data Modeling) library that provides a schema-based solution to model the data.
- **Mongoose**: Mongoose is used for schema validation and interacting with MongoDB. It ensures data integrity and provides methods for CRUD operations.
- **CORS**: The CORS middleware is used to handle cross-origin requests, allowing the frontend to interact with the backend.

### Frontend:
- **React**: The frontend is developed using React, a popular JavaScript library for building user interfaces. React helps in creating dynamic and interactive web pages with components.
- **React Router**: Used for handling navigation between pages without refreshing the page. It provides a seamless experience for users to navigate through the website.
- **CSS**: CSS is used for styling, and custom styles are applied across different components and pages.
- **Axios/Fetch**: These are used for making HTTP requests from the frontend to the backend to fetch data (like product information, user authentication, etc.).

### Development Tools:
- **Git**: Git is used for version control, ensuring that changes made to the project are tracked and can be easily reverted if necessary.
- **GitHub**: GitHub is used for remote code storage and version management. It facilitates collaboration, provides a repository for the code, and serves as a backup of the project.
- **Jest & Supertest**: These are used for backend testing, ensuring that the server and API endpoints function as expected. Jest is used for unit tests, while Supertest is used for testing API routes.

### Additional Tools:
- **dotenv**: The dotenv package is used to manage environment variables, ensuring that sensitive information like API keys, database connection strings, and other credentials are securely stored.

### Deployment:
- **MongoDB Atlas**: The MongoDB database is hosted on MongoDB Atlas, providing a fully managed cloud database service. This ensures scalability, security, and ease of access from the backend.

## 2. Backend

The backend is built using Node.js and Express. It serves as the API layer for handling user requests and interacting with the database. The main directories and files in the Backend are as follows:

### Models
This directory contains the data models `Cart.js`, `Order.js`, `Product.js`, and `User.js`, used by the application to define the structure and rules of the data stored in the database. Each file represents a specific type of data entity used in the e-commerce system.

- **Cart.js**: Defines the structure of the shopping cart and is used to manage the items a user adds to their cart before placing an order.
- **Order.js**: Represents an order placed by a user.
- **Product.js**: Describes the product details and is used to store and retrieve product data for the store.
- **User.js**: Defines user account information such as username and password.

Example Code: [Product.js](https://github.com/Celia0322/ecommerce-project/blob/main/backend/models/Product.js)

### Routes
This directory contains the route handlers or endpoints that define how the server responds to different API requests. Each file is focused on a specific feature of the application.

- **authRoutes.js**: Handles all routes related to user authentication such as:
  - Registering a new user (`POST /register`)
  - Logging in (`POST /login`)
  - Logging out or checking login status

This file connects the frontend forms to backend logic that verifies user credentials and creates or validates tokens (using JWTs).

- **productRoutes.js**: Manages routes related to product operations, such as:
  - Getting all products (`GET /products`)
  - Getting one product (`GET /products/:id`)
  - Adding a new product (`POST /products`)

These routes allow the frontend to communicate with the backend database and perform actions on product data.

Example Code: [authRoutes.js](https://github.com/Celia0322/ecommerce-project/blob/main/backend/routes/authRoutes.js)

### seed.js
Seeding the Database with Sample Data. The file is used to populate the database with initial sample product data, which is especially useful during development and testing.
- Loads environment variables using dotenv (like the MongoDB connection URI).
- Connects to the MongoDB database using Mongoose.
- Defines an array of sample products, each with name, description, price, image, and category.
- Inserts the sample data into the products collection in the database using `Product.insertMany()`.
- Closes the database connection after seeding.

Example Code: [seed.js](https://github.com/Celia0322/ecommerce-project/blob/main/backend/seed.js)

### server.js
Starting Point of the Backend Server. The file serves as the main entry point of the backend for the e-commerce web application. It sets up and runs the Express server, connects to MongoDB, and defines key API routes.
- Load Environment Variables: Uses dotenv to access sensitive config values like the database URI and server port from a `.env` file.
- Initialize Express App: Creates an Express server instance to handle HTTP requests.
- Connect to MongoDB: Connects to a MongoDB database using Mongoose for data storage.
- Set Up Middleware
  - `cors()`: Allows cross-origin requests (important for frontend-backend communication).
  - `express.json()`: Parses incoming JSON request bodies.
- Register Routes:
  - `/products`: Handles product-related routes (e.g., fetch, create, update products).
  - `/auth`: Handles user authentication routes like registration and login.
  - `/api/checkout`: Simulates a checkout process (can later be connected to order processing logic).
- Default Route: `/`: Returns a welcome message to confirm the API is working.

Example Code: [server.js](https://github.com/Celia0322/ecommerce-project/blob/main/backend/server.js)

### Middleware
- **express.json()**: Automatically parses incoming JSON data so I can use `req.body` easily.
- **cors()**: Enables Cross-Origin Resource Sharing, allowing my frontend (on a different port) to communicate with the backend.
- **Custom Error Handling Middleware**: I created a file called `errorHandler.js` to handle errors across the app.
  - It catches and responds to errors with a proper message and status code instead of crashing the server.

Example Code: [errorHandler.js](https://github.com/Celia0322/ecommerce-project/blob/main/backend/middleware/errorHandler.js)

## 3. Frontend

The frontend is developed using React with Bootstrap for styling.

### Structure
- **Components**:
  - **Navbar.js**: This is the navigation bar shown on every page. It includes links like Home, Cart, Login, etc.
  - **Navbar.css**: The styles for the Navbar to make it look nice and responsive.
  - **Context**: Used to share data across multiple components without passing props manually.
    - **AuthContext.js**: Manages user login/logout state across the app.
    - **CartContext.js**: Stores items added to the cart and makes them accessible on all pages.

- **Pages**: Each file here is a full page in my app.
  - **Home.js / Home.css**: The main landing page showing featured products or categories.
  - **Product.js / Product.css**: Shows details about a specific product.
  - **Register.js / Register.css**: A page where users can create a new account.
  - **Auth.js / Auth.css**: The login page for existing users.
  - **Cart.js / Cart.css**: Displays items the user has added to their shopping cart.
  - **Checkout.js / Checkout.css**: Where users fill in their information and place an order.
  - **OrderHistory.js / OrderHistory.css**: Shows a list of past orders the user has made.

- **Routes**: React Router helps users move between pages like Home, Cart, Product, etc., without refreshing the browser.
  - **App.js, App.css, App.test.js**
    - **App.js**: The main file that connects all the pages and routes together.
    - **App.css**: Styles for the overall layout and global elements of the app.
    - **App.test.js**: A test file for checking that the app renders correctly (used for automated testing).
  - **index.js, index.css**
    - **index.js**: The entry point of the React app. It renders the `<App />` component into the browser.
    - **index.css**: Basic global styles like font, background color, margins, etc.

Example Code: [Routes.js](https://github.com/Celia0322/ecommerce-project/blob/main/frontend/src/routes/Routes.js)

## 4. Database

The application uses MongoDB Atlas, a cloud-based NoSQL database, for storing all data. Since the database is hosted in the cloud, there is no separate database folder in the project directory. Mongoose is used throughout the backend to validate, structure, and interact with the database.

### Main Collections
- **Users**: Stores user account details and login credentials.
- **Products**: Contains information about products, such as names, descriptions, prices, images, and categories.
- **Orders**: Stores details of the user’s orders, including the products ordered, user information, and payment status.

![MongoDB Atlas Image](https://github.com/Celia0322/E-commerce-platform/blob/main/images/Mongodb%20Atlas.png?raw=true)

## 5. Basic Structure and Architecture

The project follows a client-server architecture with separate frontend and backend components.

### Frontend:
- **Built with React**: The frontend is developed using React, a popular JavaScript library for building user interfaces.
- **React Router**: Used for client-side routing to enable smooth navigation between different pages (e.g., Home, Product, Cart, Checkout).
- **Reusable Components**: The frontend is modular with reusable components such as:
  - **Navbar**: Displays the navigation menu for the user to access different pages.
  - **Product List**: Displays a list of available products for browsing.
- **Pages**: Each page corresponds to a specific route (e.g., Home, Product, Cart, Checkout).
- **Context API**: Global state management is handled using React’s Context API. This is used for managing states such as:
  - **User Authentication**: Keeps track of the logged-in user’s information.
  - **Cart Data**: Tracks items added to the shopping cart across different pages.

### Backend:
- **Built with Node.js and Express**: The backend API is developed using Node.js with the Express framework.
- **MongoDB Atlas**: The database is hosted on MongoDB Atlas, a cloud-based service that provides a fully managed NoSQL database.
- **Routes**:
  - **Product Routes (`productRoutes.js`)**: Handles operations related to product management (e.g., viewing products, adding products).
  - **Authentication Routes (`authRoutes.js`)**: Handles user login, registration, and authentication.
- **Models**: Data structures are defined using **Mongoose** to interact with the database. Models include:
  - **Product Model**: Defines the structure for product data.
  - **User Model**: Defines the structure for user data and handles user-related actions.
  - **Order Model**: Defines the structure for customer orders.
  - **Cart Model**: Handles items in the user's shopping cart.
- **Middleware**:
  - **CORS**: Handles cross-origin requests to allow frontend communication with the backend.
  - **Error Handling**: A centralized error handler ensures consistent error responses across the application.

The frontend makes HTTP requests to the backend API to fetch and manipulate data stored in MongoDB. This modular structure ensures scalability and ease of maintenance, following a **RESTful API design** for clear separation of concerns between the client and server.

## 6. Functionalities

- **Navigation**:
  - Users can navigate between different pages using navigation bar.

- **User Authentication**:
  - Register, login, and logout functionality using JWTs.
  - Password encryption for secure storage.
  - Authorization middleware to protect routes that require login.

- **Product Management**:
  - Users can view product listings and details.
  - Users can add a product to the cart.

- **Cart Functionality**:
  - Add and remove products from the cart.
  - View the cart and proceed to checkout.

- **Checkout Functionality**:
  - Users can view the order summary.
  - Users can enter shipping information, such as name, address, payment method, etc.

- **Order Management**:
  - Users can place orders and view order history.
  - Order history can be hidden when users logout to protect user privacy.

- **Testing**:
  - Jest and Supertest are used for testing the backend API to ensure that the routes and server behave as expected.

## 7. Code Quality and Documentation

- **Modular Backend Structure**: 
  - The backend is organized into clear folders such as models, routes, middleware, and controllers (if applicable), each responsible for specific tasks in the system.
- **Frontend Organization**:
  - React components are broken down into reusable parts (e.g., `Navbar.js`), and CSS files are separated by component/page for better styling management.
- **Modern JavaScript Practices**: 
  - ES6+ syntax is used throughout the project, ensuring compatibility with modern JavaScript environments.
  - Consistent naming conventions are followed for variables, functions, and files.
- **Environment Variables**: 
  - Sensitive information like database connection strings is stored in a `.env` file and accessed using the **dotenv** package.
- **Custom Middleware**: 
  - A custom error handler (`errorHandler.js`) is used to manage errors consistently across the app.
- **Documentation**:
  - The project includes comments and documentation to guide developers on key functionalities.
  - The code is structured in a logical flow, making it easier to debug and collaborate on.

## 8. Testing and Error Handling

- **Testing**:
  - Basic testing is implemented using **React Testing Library** in `App.test.js` for frontend components.
  - **Jest** and **Supertest** are used for backend testing to validate the functionality of API routes.
- **Error Handling**:
  - **Backend**: 
    - Try-catch blocks are used to catch errors in API routes like `/auth` and `/checkout`.
    - A centralized error handler (`errorHandler.js`) catches and responds to errors in a consistent format.
  - **Frontend**:
    - Users are shown error messages for failed login, registration, or order placement attempts.
    - Proper HTTP status codes (e.g., 200, 400, 500) are sent from the backend for better error tracking and debugging.
    - Logs are printed to the console for easier server-side debugging.

## 9. User Interface and Interaction

The frontend of the e-commerce website is designed to be clean, user-friendly, and responsive for an optimal user experience.

### Main Features:
- **Navigation**: 
  - A top navigation bar (implemented in `Navbar.js`) allows users to navigate easily between the pages.

![Navigation Bar Image](https://github.com/Celia0322/E-commerce-platform/blob/main/images/navigation_bar.png?raw=true)

- **Product Browsing**: 
  - Users can view products on the **Home** page (implemented in `Home.js`), with images, descriptions, and prices displayed.
 
![Homepage1](https://github.com/Celia0322/E-commerce-platform/blob/main/images/homepage1.png?raw=true)
![Homepage2](https://github.com/Celia0322/E-commerce-platform/blob/main/images/homepage2.png?raw=true)

  - Users can also view a single product information and add it to the cart.
    
![Product1](https://github.com/Celia0322/E-commerce-platform/blob/main/images/product1.png?raw=true)
![Product2](https://github.com/Celia0322/E-commerce-platform/blob/main/images/product2.png?raw=true)

- **User Authentication**: 
  - Users can register and log in via dedicated forms (**Register.js** and **Auth.js**).
  - If registration fails, an error message will appear.
  - Once logged in, users can see their order history (**OrderHistory.js**).

![Login image](https://github.com/Celia0322/E-commerce-platform/blob/main/images/login.png?raw=true)
![Register_failed image](https://github.com/Celia0322/E-commerce-platform/blob/main/images/register_failed.png?raw=true)
![Homepage1](https://github.com/Celia0322/E-commerce-platform/blob/main/images/homepage1.png?raw=true)

- **Cart Management**: 
  - Users can add items to the cart, view the cart contents, and remove items(**Cart.js**), and proceed to checkout (**Checkout.js**).
 
![Cart1](https://github.com/Celia0322/E-commerce-platform/blob/main/images/cart1.png?raw=true)
![Cart2](https://github.com/Celia0322/E-commerce-platform/blob/main/images/cart2.png?raw=true)

- **Checkout**: 
  - Users can view the product summary and enter shipping and payment information (**Checkout.js**).

![Checkout1](https://github.com/Celia0322/E-commerce-platform/blob/main/images/checkout1.png?raw=true)
![Checkout2](https://github.com/Celia0322/E-commerce-platform/blob/main/images/checkout2.png?raw=true)

- **Order History**: 
  - Users can view their past orders after logging in.

![Order History Image](https://github.com/Celia0322/E-commerce-platform/blob/main/images/orderhistory.png?raw=true)

### UI Design:
- The interface is styled using separate CSS files for each component and page (e.g., `Home.css`, `Cart.css`), which enhances the visual appeal and organization of the application.
- **React Router**: Smooth transitions between pages without refreshing the page, improving the overall user experience.
- **User Feedback**: 
  - Forms and buttons provide immediate feedback to users (e.g., success messages or errors), which helps users interact with the site easily.
  
### Future Improvements:
- **Images and Icons**: 
  - For a better user experience, images and icons can be added to the website later to improve the visual layout and make the interface more engaging.
