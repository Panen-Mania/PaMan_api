# PaMan API Prod

An deployment (vercel deployment) branch of **Panen Mania API**

# 🛍️ E-commerce Backend API

This project is a robust backend API designed to power **Panen Mania** e-commerce platform. It provides a comprehensive set of endpoints for managing users, products, orders, and other essential e-commerce functionalities. The API prioritizes security, scalability, and maintainability, making it a solid foundation for building a thriving online store.

# ❗ Disclaimer

This project was **built on CommonJS**, therefore it might not compatible with some latest version of package.

## 📖 Documentation

Read the API documentation [here](https://documenter.getpostman.com/view/49071923/2sB3dLUBwf#intro).

## 🚀 Key Features

- **User Authentication and Authorization:** Secure user registration, login, logout, and token refresh mechanisms using JWTs and Redis.
- **Product Management:** Comprehensive product listing, creation, updating, and deletion features with pagination and caching for optimal performance.
- **Order Management:** Efficient order placement, tracking, and management capabilities for both users and administrators.
- **User Profile Management:** Allows users to manage their profiles, including updating personal information and avatars.
- **Address Management:** Enables users to add, update, and manage their shipping addresses.
- **Cart Management:** Provides functionality for users to manage their shopping carts, including adding, updating, and removing items.
- **Product Rating and Reviews:** Allows users to rate and review products they have purchased.
- **Admin Panel:** Secure admin panel with functionalities for managing users, products, and orders.
- **Contact Form:** Enables users to submit inquiries through a contact form.
- **Input Validation:** Robust input validation to ensure data integrity and prevent security vulnerabilities.
- **Image Management:** Integration with Cloudinary for efficient image storage and management.
- **Caching:** Implements Redis caching to improve API performance and reduce database load.
- **Role-Based Access Control (RBAC):** Implements RBAC to control access to different functionalities based on user roles.

## 🛠️ Tech Stack

- **Backend:** Node.js, Express.js
- **Database:** PostgreSQL
- **ORM:** Prisma
- **Authentication:** JSON Web Tokens (JWT), bcryptjs
- **Session Management:** Redis, express-session, connect-redis
- **Image Storage:** Cloudinary
- **Caching:** Redis
- **Security:** helmet, cors, express-rate-limit
- **Validation:** zod, custom validation functions
- **Utilities:** uuid, dotenv, morgan
- **Other:** `jsonwebtoken`, `bcryptjs`, `uuid`

## 📦 Getting Started

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- PostgreSQL database
- Redis server (deployed)
- Cloudinary account
- Environment variables configured in a `.env` file (see `.env.example` if available)

### Installation

1.  Clone the repository:

    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2.  Install dependencies:

    ```bash
    npm install # or yarn install
    ```

3.  Configure environment variables:

    Create a `.env` file in the root directory and configure the following environment variables:

    ```
    PORT=5000
    DATABASE_URL=<PostgreSQL_connection_string>
    REDIS_URL=<Redis_connection_string>
    SESSION_SECRET=<secret_session_key>
    CLIENT_URL=<client_application_url>
    SECRET_KEY_JWT=<jwt_secret_key>
    CLOUDINARY_CLOUD_NAME=<cloudinary_cloud_name>
    CLOUDINARY_API_KEY=<cloudinary_api_key>
    CLOUDINARY_API_SECRET=<cloudinary_api_secret>
    DEFAULT_USER_AVATAR=<default_user_avatar_url>
    ```

4.  Set up the database:

    ```bash
    npx prisma migrate dev
    npx prisma db seed # if seeding is required
    npm run usfdb # custom script to update schema from db
    ```

### Running Locally

```bash
npm run dev # or yarn dev
```

The server will start on the port specified in your `.env` file (default: 5000).

## 📂 Project Structure

```
├── index.js              # Main entry point for the backend application
├── package.json          # Project dependencies and scripts
├── prisma                # Prisma ORM configuration
│   ├── schema.prisma     # Database schema definition
│   └── seed.ts           # Database seeding script (if applicable)
├── src
│   ├── config            # Configuration files
│   │   └── inputConstraint.js # Input validation constraints
│   ├── controllers       # Controller logic for handling API requests
│   │   ├── adminControllers.js       # Admin-related controllers
│   │   ├── contactControllers.js     # Contact form controllers
│   │   ├── productControllers.js     # Product-related controllers
│   │   ├── userAdressControllers.js  # User address controllers
│   │   ├── userCartControllers.js    # User cart controllers
│   │   ├── userControllers.js        # User-related controllers
│   │   ├── userOrderControllers.js   # User order controllers
│   │   └── userRatingProductsController.js # User rating controllers
│   ├── helper            # Helper functions
│   │   ├── auth.js             # Authentication helper
│   │   ├── cacheInvalidation.js# Cache invalidation helpers
│   │   ├── capitalizeFirstLetter.js # String capitalization helper
│   │   ├── common.js           # Common utility functions
│   │   ├── getCloudinaryPublicId.js # Cloudinary public ID extraction
│   │   ├── getRemainingTokenLifetime.js # Token lifetime calculation
│   │   ├── orderQuantityCheck.js # Order quantity validation
│   │   ├── pagination.js       # Pagination logic
│   │   ├── paginationCheck.js  # Pagination validation
│   │   ├── productInputCheck.js # Product input validation
│   │   ├── productQuantityCheck.js # Product quantity validation
│   │   ├── redisClient.js      # Redis client
│   │   ├── removeNullProperties.js # Object property removal
│   │   ├── serial-id-check.js  # Serial ID validation
│   │   └── userAddressInputCheck.js # User address input validation
│   ├── middleware        # Middleware functions
│   │   ├── adminAuth.js        # Admin authentication middleware
│   │   ├── cloudinary.js       # Cloudinary configuration
│   │   ├── upload.js           # File upload middleware
│   │   └── userAuth.js         # User authentication middleware
│   ├── routes            # API route definitions
│   │   ├── adminRoutes.js        # Admin routes
│   │   ├── contactRoutes.js      # Contact routes
│   │   ├── productRoutes.js      # Product routes
│   │   └── userRoutes.js         # User routes
│   └── utils             # Utility functions
```

## 📝 License

[MIT](LICENSE)

## 💖 Thanks

Thank you for checking out this project!

This README was written by [readme.ai](https://readme-generator-phi.vercel.app/).


