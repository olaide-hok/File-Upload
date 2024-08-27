# File Upload

A Node.js, Express, and MongoDB project that allows image file uploads to a server using Express File Upload. The project integrates with Cloudinary to store images on the cloud.

## Overview

This API is designed for an e-commerce store where admins can add products with images. When adding a product, the image is first uploaded to the server, stored on Cloudinary, and then the product details (name, price, and image path) are saved in the database.

### Key Features:

-   **File Upload:** Upload images to the server using Express File Upload.
-   **Cloud Storage:** Store images on Cloudinary and save the image path in the database.
-   **Product Management:** Create and retrieve product details, including the image URL.

## Tech Stack

-   **Backend:** Node.js, Express.js
-   **Database:** MongoDB
-   **Cloud Storage:** Cloudinary
-   **Authentication:** JSON Web Token (JWT)

## Packages Used

-   **dotenv:** To load environment variables from a `.env` file.
-   **express:** Web framework for Node.js.
-   **express-async-errors:** Simplifies error handling in Express.
-   **express-fileupload:** Middleware for handling file uploads.
-   **cloudinary:** Cloud storage service for managing images.
-   **jsonwebtoken:** For generating and verifying JWTs.
-   **mongoose:** MongoDB object modeling tool.
-   **http-status-codes:** Provides standard HTTP status codes.

## API Routes

### Create Product

-   **POST** `/api/v1/`
    -   Add a new product with a name, price, and image path.
    -   Image must be uploaded first using the `/uploads` route to get the image path.

### Get All Products

-   **GET** `/api/v1/`
    -   Retrieve all products with their names, prices, and image URLs.

### Upload Product Image

-   **POST** `/api/v1/uploads`
    -   Upload an image file to Cloudinary.
    -   Returns the image URL, which can be used to save the product.

## Product Model

The product schema includes the following fields:

-   **Name:** Name of the product.
-   **Price:** Price of the product.
-   **Image:** URL of the image stored on Cloudinary.

## Environment Variables

The following environment variables need to be configured in a `.env` file:

-   **MONGO_URI:** MongoDB connection string.
-   **JWT_SECRET:** Secret key for JWT.
-   **JWT_LIFETIME:** JWT expiration time.

## Getting Started

1. Clone the repository:

    ```bash
    git clone https://github.com/olaide-hok/File-Upload.git
    ```

2. Install dependencies:

    ```bash
    npm install
    ```

3. Setup Environment Variables:

    - Create a .env file in the root directory of your project.
    - Add the required environment variable MONGO_URI, JWT_SECRET, JWT_LIFETIME

4. Run the server:

    ```bash
    npm start
    ```
