# ✪ Project Title
**E-Buy: A Simple E-Commerce Platform for Browsing and Buying Products**

---

## 📝 Project Overview
**E-Buy** is a full-stack web application that allows users to browse, view, and purchase products in a streamlined online shopping experience. The purpose of the project is to simulate a simplified version of an online store with essential features of modern e-commerce.

The main target users are everyday online shoppers who expect a clean user interface and intuitive functionality.

The application allows:
- Product browsing
- Viewing details
- Adding items to the cart
- User authentication
- Checkout process

---

## 📌 Use Case Summary

| Use Case              | Implemented | Demonstration / Notes                             |
|-----------------------|-------------|---------------------------------------------------|
| Browsing Products     | Yes         | Home page shows product thumbnails with images    |
| Viewing Product Details | Yes       | Click product to open detail view                 |
| Adding Products to Cart | Yes       | Button on product page adds item to cart          |
| Viewing Cart          | Yes         | Cart page lists all selected products             |
| Making a Purchase     | Yes         | `Checkout.js` implements order summary and form   |
| User Authentication   | Yes         | Users can register/login, session stored in cookies |

🔗 Link to use cases: *[Phase 1 documentation](https://github.com/Celia0322/E-commerce-platform/blob/main/1_Definition_and_Planning.md)*

---

## ✍️ Technical Implementation

### **Frontend**
- Built using **React** (functional components + React Router)
- **Custom CSS** for layout, responsive design, product images, mobile-friendly UI

### **Backend**
- Built with **Node.js + Express**
- Handles API endpoints: products, users, cart, checkout

### **Authentication**
- **bcrypt** for password hashing
- **JWT** for session management

### **Database**
- **MongoDB** stores products, users, cart
- Product schema includes `imageURL`
- User schema supports login, registration, sessions
- Cart schema tracks user items

### **Images**
- Stored in `frontend/public/images`
- `imageURL` field used to display in list & detail views

### **Key Features**
- Fully functional **shopping cart**
- **Checkout** with form validation
- **Responsive** across desktop and mobile
- Product **images** integrated in both views

---

## 🚂 Development Process

### 🔹 Phase 1 – Planning and Design
- Selected project topic
- Defined user personas and use cases
- Created wireframes in **Figma**
- Planned DB schema, API structure, and user testing

### 🔹 Phase 2 – Initial Setup and Development
- Set up folder structure and dev environment
- Configured backend (Node.js + Express), MongoDB, frontend (React)
- Integrated frontend/backend
- Deployed basic version locally
- Implemented core features

### 🔹 Phase 2 – UI Design, Testing, and Optimization
- Improved UI and ensured feature functionality
- Performed testing and fixed bugs
- Deployed on **Azure VM**
- Completed Phase 2 report

### 🔹 Phase 3 – Feature Enhancement
- Added **product images**
- Updated schema and frontend
- Applied responsive design
- Key improvements:
  - Refactored components
  - Styled for accessibility & responsiveness

---

## ☀️ Reflection and Future Work

### ✅ What Worked Well
- Core features like cart, product details
- Image support enhanced UX
- Responsive design worked well
- JWT-based secure authentication

### 😅 Challenges
- Complex state management across components
- Layout issues with image loading on small screens
- Backend route structure needed refining
- Azure VM deployment (ports, DB config)
- Session bugs during registration/login

### 🌱 Future Improvements
- Add **admin panel** for product management
- Implement personal **order history tracking** for each user
- Add **product rating and reviews**

---

## 📊 Work Hours Log

| Date       | Time  | Task                                                                 |
|------------|-------|----------------------------------------------------------------------|
| 15.03.2025 | 0.5h  | Searched for project topics and made a decision                      |
| 16.03.2025 | 2h    | Defined user personas, use cases, DB schema, API, specs, user testing |
| 17.03.2025 | 2h    | Created wireframes in Figma and GitHub repo for Phase 1              |
| 24.03.2025 | 2h    | Created the directory and basic project structure                    |
| 25.03.2025 | 3h    | Set up environment, backend, database, frontend                      |
| 03.04.2025 | 4h    | Integrated backend & frontend, deployed simple website locally       |
| 06.04.2025 | 3h    | Designed a simple user interface                                      |
| 07.04.2025 | 4h    | Added functionality to different website sections                    |
| 09.04.2025 | 3h    | Improved UI and tested functionality                                 |
| 10.04.2025 | 3h    | Optimized functionality and added testing                            |
| 11.04.2025 | 4h    | Debugged and wrote Phase 2 report                                    |
| 12.04.2025 | 3h    | Deployed app on Azure VM and completed Phase 2 report                |
| 17.04.2025 | 3h    | Added product pictures to homepage and product view page             |
| 18.04.2025 | 3h    | Deployed updated app to Azure VM and completed Phase 3 report        |
| 19.04.2025 | 2h    | Prepared Phase 4 presentation                                        |
| 20.04.2025 | 2h    | Completed Phase 4 presentation                                       |

**🧮 Total Hours: 47.5h**

---

## 🪢 Presentation Link
*The project will be presented live.*
