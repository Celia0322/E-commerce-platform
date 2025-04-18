# Phase 3 – Extra Feature or Improvements (Optional)

## 🎯 Chosen Use Case or Feature to Improve

I chose to improve the user experience of the **Browsing Products** and **Viewing Product Details** use cases by adding product images to the application.  
This improvement was chosen because visual content plays a crucial role in e-commerce. Images help users better understand what they are buying and increase user engagement. Without images, the browsing experience would seem incomplete and boring. Adding visuals makes the app more realistic and engaging, especially for end users who are accustomed to image-rich shopping environments.

---

## 🔍 Original Definition

The original use cases defined in Phase 1 https://github.com/Celia0322/E-commerce-platform/blob/main/1_Definition_and_Planning.md were:
- **Browsing Products** – Users can browse through different categories of products.
- **Viewing Product Details** – Users can browse details of a product.

These were implemented with product names, descriptions, and prices, but no images.

---

## 🔄 Implementation

In this phase, I added image support to the products displayed in both the product list (home page) and the product detail pages.

### 🛠️ What was added or changed:
- Each product in the database was updated to include an `image` field containing a URL to a product image.
- **In the frontend**:
  - The product list view (e.g., `Home.js` and `Product.js`) was updated to display a thumbnail for each product.
  - The product detail view (e.g., `Product.js`) was modified to show a larger version of the image.
- Basic CSS was added to ensure the images display responsively and look visually appealing on different screen sizes.

---

## 🧑‍💻 Technologies and Methods Used:
- **React**: The components were updated to render images using `<img>` tags.
- **CSS**: Styling was applied to control image size, aspect ratio, and layout alignment.
- **Database or API layer**: Added an `imageURL` field to the product schema in MongoDB to store the local image path.
- **Frontend**: A new `images` folder was created inside the `frontend/public` directory to store product images. The image URLs in MongoDB were updated to reflect the correct file paths.
- **Image Handling**: Product components (e.g., `Home.js`, `Product.js`) were updated to render the images using the updated `imageURL` stored in the database.

---

## 😅 Challenges & Solutions:
- **Image loading issues**: Initially, some image URLs were broken or slow to load. To solve this, I stored product images in a local `images` folder within the `public` directory and ensured the MongoDB `imageURL` field pointed to the correct image path.
- **Layout breaking on smaller screens**: Adjusted the layout using responsive CSS (flexbox/grid and `max-width`) to ensure images and content looked balanced across all screen sizes.
- **Data structure changes**: Adding the `imageURL` field required updating both the backend MongoDB data model and the frontend components (e.g., `Home.js` and `Product.js`) to handle and display images correctly.
