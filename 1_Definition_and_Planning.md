# Project Phase 1 - Definition and Planning

This E-commerce platform allows users to browse products, add them to a shopping cart, and make purchases online. It features a user-friendly interface built with React, server-side logic handled by Node.js, and a RESTful API for managing product data and user authentication.

## 1. User Personas

Define key personas to understand the target users and their needs.

- **Alice (25 years old)** – A busy professional who shops online for convenience. She values a smooth and quick checkout process, product variety, and secure payments.
- **John (32 years old)** – A tech-savvy shopper who enjoys comparing prices, reading reviews, and exploring new products. He values detailed product descriptions and recommendations.
- **Carol (40 years old)** – A small business owner who buys supplies in bulk and needs a reliable order tracking system.

## 2. Use Cases and User Flows

### Use Cases
1. **Browsing Products** – Users can browse a list of products with categories, filters, and sorting options.
2. **Adding Products to Cart** – Users can add products to their shopping cart for future purchase.
3. **User Authentication** – Users can create an account, log in, and view past orders.
4. **Making a Purchase** – Users can review their cart, enter payment details, and complete the purchase.
5. **Admin Product Management** – Admins can add, update, or remove products and manage inventory.

### Example User Flow: Making a Purchase
1. **User visits homepage** and browses through products or categories.
2. **User adds items to cart** from product listings.
3. **User clicks on the cart** to review selected products.
4. **User proceeds to checkout**, enters shipping information, and payment details.
5. **User completes purchase** and receives a confirmation message.

## 3. UI Prototypes

The UI design should be user-friendly, ensuring a seamless shopping experience.

- **Homepage** – Displays featured products and categories. Includes a search bar and navigation menu.
- **Product Page** – Shows product details, including images, description, price, and “Add to Cart” buttons.
- **Cart Page** – Lists selected items, total price, and provides checkout options.
- **Checkout Page** – Includes forms for shipping information, payment, and order review.
- **User Account Page** – Includes options for users to log in or sign up.


## 4. Information Architecture and Technical Design

### Information Architecture
The site should include these sections:
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

