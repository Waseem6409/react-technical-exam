## React Developer Code Challenge (React, Redux Toolkit, TypeScript, SCSS)

This challenge is designed to assess your skills and understanding of modern web development technologies focusing on React with Redux Toolkit, TypeScript, and SCSS. You are provided with a starter codebase that you need to complete and deploy to a public repository.

**Objective:**

- **Fork and clone the provided public Git repository.**
- **Complete the application to fulfill the functionalities and technical requirements mentioned below.**
- **Deploy the application to a platform of your choice (e.g., Heroku, Netlify).**
- **Submit the link to your deployed application and the public repository URL for evaluation.**

**Project Details:**

The application will consist of five pages:

1.  **Signup:**
    - Users can create new accounts with name, email, and password.
    - Implement proper validation for email format and password strength (minimum 8 characters).
2.  **Login:**
    - Existing users can log in with their email and password.
    - Store user authentication information securely (e.g., using JWT tokens).
3.  **Update Profile:** (Requires authentication)
    - Allow logged-in users to update their profile information (username, email, password).
    - Implement proper authorization checks using the provided token in the header (auth bearer).
    - Validate password length (minimum 8 characters) if user updates it.
4.  **Products:** (Requires authentication)
    - Display a list of products with details (e.g., name, description, price).
    - Implement an API to fetch product data using `/products` endpoint.
    - Must have search box to search products, must have filter to sort products based on price(asc or desc) or name (asc or desc)
5.  **Product Detail:** (Requires authentication)
    - Allow users to view the details of a specific product fetched using the `/products/:productId` endpoint.
    - Include relevant information like name, description, price,ratings, and potentially an image.

**Technical Requirements:**

- Use React for the user interface.
- Manage global state using Redux Toolkit.
- Implement API calls using Redux Toolkit's data fetching capabilities.
- Use TypeScript for strong typing and code safety.
- Style the application using SCSS for improved maintainability and organization.

**Routing & Access Control:**

- Only the Signup and Login routes will be accessible to unauthorized users.
- The Products page will be the application's **homepage**.
- Clicking on a product card should navigate the user to the `/product/:productId` route, displaying the specific product details.

**API Endpoints:**

**Base URL:** https://matech-interview-97550e726f69.herokuapp.com

**Authentication:**

- All requests except `/auth/login ` and `/auth/signup ` require user authentication.
- Include the user's JWT token in the request header with `Authorization: Bearer <token>`.

**Endpoints (same as previous version):**

- **POST /auth/signup:**
  - **Request Body:**
    - `name`: String (required)
    - `email`: String (required, must be a valid email format)
    - `password`: String (required, minimum 8 characters)
  - **Response:**
    - On success, returns a JSON object with user information and a token.
    - On failure, returns an error message indicating the reason for failure.
- **POST /auth/login:**
  - **Request Body:**
    - `email`: String (required)
    - `password`: String (required, minimum 8 characters)
  - **Response:**
    - On success, returns a JSON object containing a token.
    - On failure, returns an error message indicating the reason for failure.
- **POST /auth/update:** (requires authentication)
  - **Request Body:** (can be any combination of the following)
    - `name`: String
    - `email`: String (must be a valid email format)
    - `password`: String (minimum 8 characters)
  - **Response:**
    - On success, returns a JSON object with the updated user information.
    - On failure, returns an error message indicating the reason for failure.
- **GET /products:** (requires authentication)
  - **Response:**
    - Returns a JSON array containing product information (e.g., name, description, price).
  - **Error:**
    - On failure, returns an error message.
- **GET /products/:productId** (requires authentication)
  - **Path Parameter:**
    - `productId`: String (ID of the product)
  - **Response:**
    - On success, returns a JSON object containing the specific product details.
    - On failure, returns an error message.

**Additional Requirements:**

- Use the provided logo in the `assets
- Must have a loading indicator showing user that api is being called
- There must a logout button to logout the user
