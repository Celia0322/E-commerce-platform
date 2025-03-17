# Project Phase 1 - Definition and Planning

This E-commerce platform allows users to browse products, add them to a shopping cart, and make purchases online. It features a user-friendly interface built with React, server-side logic handled by Node.js, and a RESTful API for managing product data and user authentication.

## 1. User Personas

Define key personas to understand the target users and their needs.

- **Alice (25 years old)** – A busy professional who shops online for convenience. She values a smooth and quick checkout process, product variety, and secure payments.
- **John (32 years old)** – A tech-savvy shopper who enjoys comparing prices, reading reviews, and exploring new products. He values detailed product descriptions and recommendations.
- **Carol (40 years old)** – A small business owner who buys supplies in bulk and needs a reliable order tracking system.

## 2. Use Cases and User Flows

### Use Cases
- **Browsing Products** – Users can browse a list of products with categories, filters, and sorting options.
- **Adding Products to Cart** – Users can add products to their shopping cart for future purchase.
- **User Authentication** – Users can create an account, log in, and view past orders.
- **Making a Purchase** – Users can review their cart, enter payment details, and complete the purchase.
- **Admin Product Management** – Admins can add, update, or remove products and manage inventory.

### Example User Flow: Making a Purchase
- **User visits homepage** and browses through products or categories.
- **User adds items to cart** from product listings.
- **User clicks on the cart** to review selected products.
- **User proceeds to checkout**, enters shipping information, and payment details.
- **User completes purchase** and receives a confirmation message.

## 3. UI Prototypes

The UI design will be user-friendly, ensuring a seamless shopping experience. The basic idea of ​​the UI is presented through the Figma prototype below.

- **Homepage** – Displays featured products and categories. Includes a search bar and navigation menu.
  
  <img width="631" alt="homepage" src="https://github.com/user-attachments/assets/8ec08446-a036-4c05-86c0-cdf5b2eb4060" />

- **Product Page** – Shows product details, including images, description, price, and “Add to Cart” buttons.

  <img width="634" alt="productpage" src="https://github.com/user-attachments/assets/6aa23165-67ce-45ab-8561-8861bf5756c8" />

- **Cart Page** – Lists selected items, total price, and provides checkout options.

  <img width="635" alt="cartpage" src="https://github.com/user-attachments/assets/badcb331-4d2b-4daa-9d78-2451fd7a7339" />

- **Checkout Page** – Includes forms for shipping information, payment, and order review.

  <img width="466" alt="checkoutpage" src="https://github.com/user-attachments/assets/0bce4d9b-3692-477e-ad4f-c913fcb2e1e6" />

- **User Account Page** – Includes options for users to log in or sign up.

  <img width="630" alt="loginpage" src="https://github.com/user-attachments/assets/4714f0ad-b2ac-4d78-b18e-7603228e2f01" />



## 4. Information Architecture and Technical Design

### Information Architecture
The site basically includes these sections:
- **Homepage** – Displays a variety of products, categories, and promotional content.
- **Product Listings** – Allows users to filter products by category, price, and other attributes.
- **Cart** – Where users review their selected items.
- **Checkout** – Allows for the purchase process with shipping and payment details.
- **User Account** – For users to manage their profile and orders.
- **Admin Dashboard** – Allows product management and inventory control.

### Technical Design
- **Frontend** – React (provides an interactive and responsive user interface).
  - **Components**: Header, Product List, Product Card, Cart, Checkout Form, Login/Signup Form.
  - **State Management**: Use React Context or Redux for managing cart data and user authentication.

- **Backend** – Node.js with Express (handles server-side logic and API endpoints).
  - **API Endpoints**:
    - **GET /products** – Fetch product data.
    - **POST /cart** – Add items to the cart.
    - **POST /checkout** – Process the order.
    - **POST /auth/login** – Handle user authentication.
    - **POST /auth/signup** – Handle user registration.

- **Database** – MongoDB (stores user data, product information, orders).
  - **Collections**: Users, Products, Orders, Cart.

## 5. Project Management and User Testing

### Project Management
- **Tools Used**: Jira (for task tracking), GitHub (for version control), Trello (for sprint planning).
- **Milestones**:  
  - **Week 1**: Define project requirements, create wireframes, set up repositories.  
  - **Week 2**: Develop frontend components and set up Node.js backend.  
  - **Week 3**: Integrate frontend with REST API, implement user authentication.  
  - **Week 4**: Test with users (focus on usability, checkout process, and admin features), fix issues.  

### User Testing Plan
- **Target Testers**: E-commerce shoppers and admin users.
- **Methods**: Observe users while browsing products, adding items to the cart, and completing purchases. Collect feedback and fix usability issues.

