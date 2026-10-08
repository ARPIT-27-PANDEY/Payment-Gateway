# 🛒 E-Commerce Website with Stripe Payment Gateway

A full-stack **e-commerce website with an integrated Stripe payment gateway**, designed to provide an end-to-end shopping and transaction workflow.

The application allows users to browse and filter products, add products to a shopping cart, proceed through checkout, and complete online payments through **Stripe Gateway**. The backend is developed using **Express.js**, while **MongoDB** is used to persist customer details, product information, cart data, and order history.

---

## 📌 Overview

The project was developed as a complete e-commerce application, with the **payment gateway implemented as an integral part of the checkout process**.

The major components are:

```text
Product Browsing
       │
       ▼
Product Filtering
       │
       ▼
Shopping Cart
       │
       ▼
Checkout
       │
       ▼
Express.js Backend
       │
       ├───────────────┐
       │               │
       ▼               ▼
    MongoDB          Stripe
       │               │
       │         Payment Processing
       │               │
       └───────┬───────┘
               ▼
         Order Completion
```

The project therefore combines:

- **Frontend e-commerce functionality**
- **Backend API development**
- **Payment gateway integration**
- **Database management**
- **Order and transaction processing**

---

# 🎯 Objectives

The primary objectives of the project are:

- Build a functional e-commerce frontend.
- Implement product browsing and filtering.
- Provide shopping cart functionality.
- Implement a complete checkout workflow.
- Develop backend APIs for cart and transaction handling.
- Integrate **Stripe Gateway** for online payment processing.
- Store customer and product information in MongoDB.
- Maintain order history for completed transactions.
- Connect the frontend, backend, database, and payment gateway into one workflow.

---

# ✨ Features

## 🛍️ E-Commerce Features

- Product listing
- Product filtering
- Product selection
- Shopping cart
- Add/remove products from cart
- Cart management
- Checkout workflow
- Order processing

## 💳 Payment Gateway Features

- Stripe payment gateway integration
- Payment initiation from checkout
- Backend transaction handling
- Payment status handling
- Integration of payment processing with order creation
- Secure payment workflow through Stripe

## ⚙️ Backend Features

- Express.js REST APIs
- Cart handling APIs
- Transaction-related APIs
- Customer data management
- Product data management
- Order history management
- Communication between frontend, Stripe, and MongoDB

## 🗄️ Database Features

MongoDB is used to store:

- Customer details
- Product information
- Cart-related data
- Order history
- Transaction-related information

---

# 🏗️ System Architecture

The project follows a full-stack architecture in which the frontend communicates with an Express.js backend, while the backend coordinates database operations and payment processing.

```text
                         ┌─────────────────┐
                         │      User       │
                         └────────┬────────┘
                                  │
                                  ▼
                    ┌─────────────────────────┐
                    │     E-Commerce          │
                    │       Frontend          │
                    │                         │
                    │  • Products             │
                    │  • Filtering            │
                    │  • Cart                 │
                    │  • Checkout             │
                    └────────────┬────────────┘
                                 │
                                 │ API Requests
                                 ▼
                    ┌─────────────────────────┐
                    │      Express.js         │
                    │        Backend          │
                    │                         │
                    │  • Cart Handling        │
                    │  • Transactions         │
                    │  • Order Processing     │
                    └────────────┬────────────┘
                                 │
                       ┌─────────┴─────────┐
                       │                   │
                       ▼                   ▼
              ┌────────────────┐   ┌────────────────┐
              │    MongoDB     │   │     Stripe     │
              │                │   │    Gateway     │
              │ • Customers    │   │                │
              │ • Products     │   │ • Payments     │
              │ • Orders       │   │ • Transactions │
              │ • Cart Data    │   │ • Status       │
              └────────────────┘   └────────────────┘
```

---

# 🛒 E-Commerce Workflow

The application follows a standard online shopping workflow.

## 1. Product Browsing

Users can browse the products available on the platform.

```text
               Product Catalog
                     │
                     ▼
              Product Listing
                     │
                     ▼
               Product Filter
                     │
                     ▼
               Select Product
```

Product filtering makes it easier for users to find relevant products.

---

## 2. Add to Cart

Users can add selected products to their shopping cart.

```text
Product
   │
   ▼
Add to Cart
   │
   ▼
Shopping Cart
   │
   ├── Update Quantity
   ├── Remove Product
   └── Review Cart
```

Cart operations are handled through backend APIs.

---

## 3. Checkout

After reviewing the cart, the customer proceeds to checkout.

```text
Shopping Cart
      │
      ▼
   Checkout
      │
      ▼
Order Information
      │
      ▼
Payment Initiation
```

---

# 💳 Stripe Payment Gateway

The payment gateway is a core component of the e-commerce checkout workflow.

Instead of handling card/payment processing directly within the application, the system integrates **Stripe** to process online transactions.

The payment flow is:

```text
                   Customer
                       │
                       ▼
                  Shopping Cart
                       │
                       ▼
                    Checkout
                       │
                       ▼
                Express.js API
                       │
                       ▼
               Stripe Gateway
                       │
              ┌────────┴────────┐
              │                 │
              ▼                 ▼
        Payment Success    Payment Failure
              │                 │
              ▼                 ▼
        Create/Complete      Handle Error
             Order
              │
              ▼
           MongoDB
```

This integration allows the payment process to remain connected with the application's order workflow.

---

# 🔄 Payment Transaction Flow

The complete transaction lifecycle can be represented as:

```text
┌──────────────────────┐
│   User Adds Product  │
│      to Cart         │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│       Checkout       │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  Frontend Sends      │
│ Payment Request      │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│     Express.js       │
│       Backend        │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   Stripe Gateway     │
│                      │
│ Payment Processing   │
└──────────┬───────────┘
           │
      ┌────┴─────┐
      │          │
      ▼          ▼
   Success     Failure
      │          │
      ▼          ▼
Create Order   Error Response
      │
      ▼
┌──────────────────────┐
│       MongoDB        │
│                      │
│ Store Order Details  │
└──────────────────────┘
```

---

# ⚙️ Backend API Layer

The backend is built using **Express.js** and acts as the communication layer between the frontend, database, and Stripe.

The backend is responsible for operations such as:

### Cart Handling

- Adding products to the cart
- Updating cart information
- Removing products
- Retrieving cart contents

### Transaction Handling

- Receiving checkout/payment requests
- Processing payment-related operations
- Communicating with Stripe
- Handling payment responses
- Maintaining transaction state

### Order Handling

- Creating order records
- Associating orders with customers
- Storing purchased products
- Maintaining order history

The architecture can be viewed as:

```text
Frontend
   │
   │ HTTP Request
   ▼
Express.js API
   │
   ├───────────────► MongoDB
   │
   └───────────────► Stripe
```

---

# 🗄️ MongoDB Database

MongoDB is used as the application's persistent database.

The database stores information necessary for smooth e-commerce operations.

## Customer Details

Stores information associated with customers.

```text
Customer
├── Customer ID
├── Name
├── Contact Information
└── Other Customer Details
```

## Product Information

Stores product-related information.

```text
Product
├── Product ID
├── Product Name
├── Price
├── Category
└── Other Product Information
```

## Order History

Completed and processed orders can be stored for future retrieval.

```text
Order
├── Order ID
├── Customer
├── Products
├── Amount
├── Payment Status
└── Order Information
```

This provides persistent storage for the e-commerce application and allows the system to maintain customer and transaction history.

---

# 🔗 Frontend–Backend–Stripe Integration

One of the major aspects of the project is connecting the different application layers.

```text
┌───────────────────────────────┐
│          Frontend             │
│                               │
│ Products → Cart → Checkout    │
└───────────────┬───────────────┘
                │
                │ HTTP / API
                ▼
┌───────────────────────────────┐
│          Express.js           │
│            Backend            │
│                               │
│ Cart / Transaction / Orders   │
└───────────────┬───────────────┘
                │
          ┌─────┴─────┐
          │           │
          ▼           ▼
    ┌──────────┐ ┌──────────┐
    │ MongoDB  │ │  Stripe  │
    └──────────┘ └──────────┘
```

This separation keeps the responsibilities of each component well defined.

---

# 🔐 Payment Security

Payment processing involves sensitive information and therefore requires secure handling.

The application delegates payment processing to **Stripe**, rather than implementing payment-card processing logic directly.

Sensitive Stripe credentials should never be exposed in frontend code.

For example:

```text
❌ Do not expose:
Stripe Secret Key
Database Credentials
Private API Credentials
```

These should remain server-side and be stored using environment variables.

Example:

```env
STRIPE_SECRET_KEY=your_secret_key
MONGODB_URI=your_mongodb_connection_string
```

> Never commit real credentials, API keys, database passwords, or secret keys to GitHub.

---

# 🧩 Technology Stack

## Frontend

- **HTML**
- **CSS**
- **JavaScript**

The frontend provides:

- Product listing
- Product filtering
- Cart interface
- Checkout interface

## Backend

- **Node.js**
- **Express.js**

Used for:

- REST APIs
- Cart management
- Transaction handling
- Order processing
- Stripe communication
- Database communication

## Database

- **MongoDB**

Used for:

- Customer details
- Product information
- Cart data
- Order history

## Payment

- **Stripe**

Used for:

- Online payment processing
- Transaction handling
- Payment status management

---

# 📂 Project Structure

A logical organization of the complete application is:

```text
Payment-Gateway/
│
├── frontend/
│   ├── index.html
│   ├── css/
│   ├── js/
│   ├── components/
│   ├── products/
│   ├── cart/
│   └── checkout/
│
├── backend/
│   ├── server.js
│   ├── routes/
│   │   ├── cart.js
│   │   ├── payment.js
│   │   └── order.js
│   │
│   ├── controllers/
│   ├── models/
│   │   ├── Customer.js
│   │   ├── Product.js
│   │   └── Order.js
│   │
│   └── config/
│
├── package.json
├── package-lock.json
└── README.md
```

> The exact source-tree organization may vary depending on how the e-commerce frontend and backend were maintained.

---

# 🚀 Getting Started

## Prerequisites

Make sure the following are installed:

- Node.js
- npm
- MongoDB or MongoDB Atlas
- Stripe account

Check Node.js and npm:

```bash
node --version
npm --version
```

---

# 📥 Installation

Clone the repository:

```bash
git clone https://github.com/ARPIT-27-PANDEY/Payment-Gateway.git
```

Navigate into the project:

```bash
cd Payment-Gateway
```

Install dependencies:

```bash
npm install
```

---

# ⚙️ Environment Configuration

Create a `.env` file for server-side configuration.

Example:

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
STRIPE_SECRET_KEY=your_stripe_secret_key
```

Do not upload the `.env` file to GitHub.

Add it to `.gitignore`:

```gitignore
.env
node_modules/
```

---

# ▶️ Running the Application

Start the backend server:

```bash
npm start
```

Start the frontend according to the frontend project configuration.

For a Vite-based frontend, the development command is:

```bash
npm run dev
```

The frontend communicates with the Express.js backend through HTTP APIs.

---

# 🧪 Stripe Testing

Stripe provides a test environment for development.

The recommended development flow is:

```text
E-Commerce Checkout
        │
        ▼
Stripe Test Environment
        │
   ┌────┴────┐
   │         │
   ▼         ▼
Success    Failure
```

Use Stripe's official test credentials/cards when testing payment flows.

Never use real customer payment information during development or testing.

---

# 🧾 Order Management

After a successful transaction, the application can associate the payment with the corresponding order.

```text
Customer
   │
   ▼
Cart
   │
   ▼
Checkout
   │
   ▼
Payment
   │
   ▼
Payment Success
   │
   ▼
Create Order
   │
   ▼
Store in MongoDB
```

This connects payment processing with the actual e-commerce order lifecycle.

---

# 🔄 Complete End-to-End Workflow

```text
                          USER
                           │
                           ▼
                  ┌─────────────────┐
                  │ Browse Products │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │ Filter Products │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │   Add to Cart   │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │     Checkout    │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │   Express.js    │
                  │      API        │
                  └───────┬─┬───────┘
                          │ │
              ┌───────────┘ └────────────┐
              │                          │
              ▼                          ▼
       ┌─────────────┐            ┌─────────────┐
       │   Stripe    │            │   MongoDB   │
       │   Gateway   │            │             │
       │             │            │ Customers   │
       │ Transaction │            │ Products    │
       │ Processing  │            │ Orders      │
       └──────┬──────┘            └─────────────┘
              │
              ▼
       Payment Status
              │
        ┌─────┴─────┐
        │           │
        ▼           ▼
    Successful    Failed
        │           │
        ▼           ▼
   Order Created   Error
        │
        ▼
     MongoDB
```

---

# 📊 Project Highlights

### Full-Stack E-Commerce Development

Built a basic e-commerce application with:

- Product filtering
- Shopping cart
- Checkout workflow

### Payment Gateway Integration

Integrated **Stripe Gateway** into the e-commerce checkout flow for online transaction processing.

### Backend API Development

Developed **Express.js APIs** for:

- Cart handling
- Transaction processing
- Order-related operations

### Database Management

Used **MongoDB** to manage:

- Customer details
- Product information
- Order history

### System Integration

Connected the:

```text
Frontend
   +
Express.js Backend
   +
MongoDB
   +
Stripe
```

into an integrated e-commerce transaction workflow.

---

# 🧠 Key Learning Outcomes

Through this project, the following concepts were explored:

- Full-stack web application development
- REST API development
- E-commerce architecture
- Shopping cart management
- Checkout workflows
- Payment gateway integration
- Stripe payment processing
- MongoDB database management
- Backend transaction handling
- Frontend-backend communication
- Secure handling of payment credentials

---

# 🔮 Future Improvements

The project can be extended with:

- User authentication and authorization
- JWT-based authentication
- Product administration dashboard
- Inventory management
- Order tracking
- Payment webhook handling
- Transaction verification
- Refund management
- Coupon and discount systems
- Product reviews and ratings
- Email notifications
- Payment and order analytics
- Dockerized deployment
- Cloud deployment

---

# ⚠️ Security Disclaimer

This project is intended for **educational and development purposes**.

A production-grade payment system requires additional measures such as:

- Server-side payment verification
- Webhook validation
- Authentication and authorization
- Input validation
- Rate limiting
- Secure credential management
- Database security
- Fraud detection
- Logging and monitoring
- Proper error handling
- Compliance with applicable payment and data-security requirements

Never commit Stripe secret keys or other sensitive credentials to the repository.

---

# 👨‍💻 Author

**Arpit Kumar Pandey**

Indian Institute of Technology Roorkee

GitHub:

https://github.com/ARPIT-27-PANDEY

---

# 🔗 Repository

https://github.com/ARPIT-27-PANDEY/Payment-Gateway

---

# ⭐ Project Summary

```text
                  FULL-STACK E-COMMERCE
                           │
             ┌─────────────┴─────────────┐
             │                           │
             ▼                           ▼
       E-Commerce UI                Express.js
             │                           │
      ┌──────┼──────┐            ┌──────┴──────┐
      │      │      │            │             │
      ▼      ▼      ▼            ▼             ▼
   Product  Cart  Checkout     MongoDB      Stripe
                                  │             │
                                  │             │
                                  └──────┬──────┘
                                         ▼
                                  Order / Payment
                                      Workflow
```

**Built a complete e-commerce workflow with product filtering, cart and checkout functionality, Express.js backend APIs, MongoDB data management, and Stripe-based online payment processing.**
