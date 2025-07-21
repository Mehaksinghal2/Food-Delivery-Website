# Food-Delivery-Website

**Project Description**
The Food Delivery Website is a full-stack web application designed to provide a seamless food ordering experience. Users can browse menus, add items to their cart, place orders, and track them in real-time. The frontend is built using React, while the backend is powered by Node.js and MongoDB, ensuring efficient data management and a responsive user interface.

**Technical Decisions and Overview**

**Frontend**
* Framework: React.js for building a responsive and dynamic user interface.
* Routing: Utilized React Router for smooth client-side navigation across pages like Home, Cart, Login, and Orders.
* State Management: Centralized state using React Context (StoreContext.jsx) to handle global data like cart contents and user authentication.
* UI Components: Modular structure with reusable components (e.g., NavBar, FoodDisplay, PaymentForm, etc.).
* Styling: CSS for layout and styling with responsive design across desktop, tablet, and mobile screens.
* Authentication: OTP-based login and verification flow implemented with secure input handling.
* Form Validation: Client-side validation for inputs such as phone numbers, addresses, and food quantities.

**Admin Panel**
* Framework: React.js with Vite for fast development and optimized builds.
* Folder Structure: Organized into Navbar, Sidebar, and pages like Add, List, and Orders to separate concerns and improve maintainability.
* Routing: Admin dashboard navigation is managed through nested routes and layout components.
* State Handling: React hooks like useState, useEffect, and sometimes context or props for passing data between components.
* UI/UX: Clean, minimal dashboard interface for managing food items and orders with real-time updates.
* Data Operations: Admin can add new food items, edit/delete existing ones, and monitor customer orders.
* Form Handling: Admin input forms use validation for food item details to prevent invalid submissions.

**Backend**
* Runtime: Node.js with Express.js for handling HTTP requests and middleware.
* Database: MongoDB for document-oriented data storage and flexible schemas using Mongoose models (UserModel, OrderModel, FoodModel, etc.).
* API Endpoints: RESTful routes for resources like:
  * /api/user
  * /api/food
  * /api/order
  * /api/cart
  * /api/payment
* Controllers: Business logic is encapsulated in controllers to keep route files clean and focused.
* Authentication: OTP-based system with possible JWT integration for protected routes.
* Middleware: auth.js used to restrict access to authenticated users or roles.
* File Uploads: Folder (uploads/) used for food image storage, configured in backend routes.
* Error Handling: Consistent error responses for client and server-side issues.

**Data Management**
* Database: MongoDB is used as the primary database due to its flexibility in storing structured and semi-structured data, perfect for handling food items, orders, users, and cart information.
* Data Models:
  * UserModel.js: Stores user details including contact info, credentials, and verification status.
  * FoodModel.js: Contains information about food items such as name, description, image, price, and availability.
  * OrderModel.js: Records each order placed, linking users to their selected items, quantities, payment status, and delivery progress.
  * OtpModel.js: Temporarily stores OTPs for login/signup authentication.
* CRUD Operations:
  * Full Create, Read, Update, Delete functionality is implemented across all entities (users, food, orders).
  * RESTful API endpoints enable interaction between frontend and backend for managing data securely and efficiently.
* Cart Management: Cart data is managed on the frontend using Context API and reflected in the backend via CartRoutes.js.
* Security:
  * Data validation using Mongoose schemas.
  * Authentication and authorization enforced via middleware.
  * Sensitive fields like passwords or OTPs are securely managed (hashed or time-limited).
* Uploads: Images and media associated with food items are handled in the /uploads directory, ensuring dynamic rendering of food visuals on the client side.

**Setup Instructions**
**Prerequisites**
* Node.js
* MongoDB

**Installation**
* Clone the Repository
  ```bash
  git clone https://github.com/Mehaksinghal2/food-delivery-website.git
  cd food-delivery-website
  ```
* Backend Setup
  ```bash
  cd backend
  npm install
  ```
* Configure Environment Variables
  * Create a .env file in the backend folder:
    ```bash
    MONGO_URL = "mongodb://localhost:27017/fooddelivery"
    SECRET_KEY = "Random#Key"
    EMAIL = "enter email for otp "
    PASSWORD = "enter password for otp "
    ```
* Run the Server:
  ```bash
  npm start
  ```
  * The backend will run at http://localhost:4000.

* Frontend Setup
  ```bash
  cd frontend
  npm install
  npm start
  ```
  * The user frontend will run at http://localhost:5173.

* Admin Panel Setup
  ```bash
  cd admin
  npm install
  npm start
  ```
**Project Structure**

**Backend**

This folder contains the server-side logic using Node.js and Express, with MongoDB as the database.
* config/ – Configuration files (e.g., db.js for MongoDB connection).
* controllers/ – Business logic for each resource:
  * FoodController.js, OrderController.js, UserController.js, CartController.js
* middleware/ – Middleware functions (e.g., auth.js for protected routes).
* models/ – Mongoose models for defining schemas:
  * UserModel.js, OrderModel.js, FoodModel.js, OtpModel.js
* routes/ – Express route definitions:
  * userRoutes.js, foodRoutes.js, orderRoutes.js, cartRoutes.js, paymentRoutes.js
* uploads/ – Folder to store image files or other static resources (e.g., food item images).

**Frontend**

This folder hosts the main user-facing frontend built with React. It handles customer interactions like browsing food, placing orders, signing up, and payments.
* src/components/ – Modular UI components like:
  * Header, Footer, NavBar
  * FoodDisplay, FoodItem, FoodPopUp
  * PaymentForm, AppDownload, ExploreMenu
* src/context/ – Global context using React Context API (StoreContext.jsx) for managing cart and user state.
* src/pages/ – Different screens/pages for user journey:
  * Home/, Login/, SignUp/
  * Cart/, PlaceOrder/, MyOrders/
  * Otp/, Verify/ – for OTP-based authentication.
    
**Admin**

This folder contains the admin panel built with React and Vite. It allows admins to manage food items, orders, and users through a responsive dashboard.
* public/ – Static files for the admin app.
* src/assets/ – Images and static resources used in admin UI.
* src/components/ – Reusable UI components like Navbar and Sidebar.
* src/pages/ – Page-level components such as:
  * Add/ – Form to add new food items.
  * List/ – View and manage existing food items.
  * Orders/ – View and manage placed orders.
* App.jsx – Main component holding route logic.
* main.jsx – Application entry point.
* index.css – Global styles.
  
**Features**
* User Signup/Login with OTP verification.
* Browse menu and view food items.
* Add items to cart and manage quantities.
* Place orders and track them.
* View past orders.
* Admin panel to add/remove food items and manage orders.
* Payment integration ready (via PaymentForm component).
* Centralized state management using Context API.

**Testing**
Use Postman or ThunderClient to test endpoints such as:
* POST /api/user/register
* POST /api/food
* GET /api/orders
* PUT /api/order/:id
* POST /api/verify-otp

**Future Enhancements**
* Mobile app using React Native.
* Live order tracking with WebSocket.
* Admin dashboard with analytics.
* Multi-language & currency support.
* AI-based food recommendations.
