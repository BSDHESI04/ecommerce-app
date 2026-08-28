# E-Commerce App

A full-stack e-commerce application with a customer storefront, shopping cart, checkout flow, and admin dashboard for managing products and orders.

## Overview

This project is split into three apps:

- Frontend: customer-facing storefront built with React + Vite + Tailwind CSS
- Admin: internal dashboard for managing products, view orders, and updating status
- Backend: Express API connected to MongoDB, Cloudinary, and Stripe

## Features

### Customer Storefront
- Product listing and category browsing
- Search and filtering support
- Product detail pages with sizes and pricing
- Add to cart and quantity management
- Cart totals and checkout flow
- Order placement with Cash on Delivery (COD)
- Stripe payment integration
- Order tracking and verification page

### Admin Dashboard
- Secure admin login
- Add new products with multiple images
- Remove products from catalog
- View all customer orders
- Update order status

### Backend Services
- MongoDB database for users, products, and orders
- JWT-based authentication
- Cloudinary image uploads
- Stripe payment session handling

## Tech Stack

- React
- Vite
- Tailwind CSS
- Express.js
- MongoDB + Mongoose
- Cloudinary
- Stripe
- JWT
- Axios

## Project Structure

```bash
.
├── admin/
│   ├── src/
│   ├── package.json
│   └── vite.config.js
├── backend/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── package.json
│   └── server.js
├── frontend/
│   ├── src/
│   ├── package.json
│   └── vite.config.js
├── .gitignore
└── README.md
```

## Prerequisites

Before running the project, make sure you have:

- Node.js 18+ installed
- MongoDB instance or MongoDB Atlas connection string
- Cloudinary account and API keys
- Stripe account and secret key

## Installation

1. Clone the repository

```bash
git clone <repository-url>
cd ecommerce-app
```

2. Install dependencies for each app

```bash
cd backend && npm install
cd ../frontend && npm install
cd ../admin && npm install
```

## Environment Variables

Create a `.env` file inside the `backend` folder with the following variables:

```env
PORT=4000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD=your_admin_password
CLOUDINARY_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_SECRET_KEY=your_cloudinary_secret
STRIPE_SECRET_KEY=your_stripe_secret_key
```

Create a `.env` file inside both the `frontend` and `admin` folders:

```env
VITE_BACKEND_URL=http://localhost:4000
```

## Running the Application

### Start the backend

```bash
cd backend
npm run server
```

The backend runs on:

- http://localhost:4000

### Start the customer frontend

```bash
cd frontend
npm run dev
```

The storefront runs on the Vite local development port (typically http://localhost:5173).

### Start the admin panel

```bash
cd admin
npm run dev
```

The admin app runs on its own Vite local development port (typically http://localhost:5174).

## Default Admin Login

Use the credentials defined in the backend environment variables:

- Email: `ADMIN_EMAIL`
- Password: `ADMIN_PASSWORD`

## API Overview

The backend exposes the following major routes:

- `/api/user/login` — customer login
- `/api/user/register` — customer register
- `/api/user/admin` — admin login
- `/api/product/list` — get products
- `/api/product/add` — add product (admin only)
- `/api/product/remove` — remove product (admin only)
- `/api/cart/add` — add to cart
- `/api/cart/get` — fetch user cart
- `/api/cart/update` — update cart quantity
- `/api/order/place` — place COD order
- `/api/order/stripe` — create Stripe checkout session
- `/api/order/verifyStripe` — verify payment status
- `/api/order/list` — list all orders (admin only)
- `/api/order/status` — update order status (admin only)

## Notes

- The customer app and admin app are designed to communicate with the same backend.
- Cloudinary is used for uploading and storing product images.
- Stripe is used for online payment processing.
- Product and order data are stored in MongoDB.

## License

This project is provided for learning and demo purposes.
