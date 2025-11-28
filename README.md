### ⛓️‍💥Link to Access the Project Folder: https://drive.google.com/file/d/1xh6pYQ1ScZQ8-ali-9i99OYKYNUl62b8/view?usp=sharing

# 🥤 Milky Shaky Custom Drinks - Order Management System

A modern, full-stack web application for ordering custom milkshakes online with pickup scheduling. Built with React, Node.js, Express, and PostgreSQL.

---

## 📋 Table of Contents

1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Technology Stack](#technology-stack)
4. [Prerequisites](#prerequisites)
5. [Installation Guide](#installation-guide)
6. [Running the Application](#running-the-application)
7. [User Guide](#user-guide)
8. [Manager Guide](#manager-guide)
9. [API Documentation](#api-documentation)
10. [Troubleshooting](#troubleshooting)

---

## 🎯 Project Overview

**Milky Shaky** is an online ordering system that allows customers to:
- Create custom milkshakes by selecting flavours, toppings, and consistency
- Schedule pickup times at their preferred restaurant location
- Make secure payments online
- Receive email confirmations with order details
- Track order history and status

**The Problem:** Long queues at Milky Shaky restaurants were causing customers to leave without ordering, as it takes 10-15 minutes to prepare each custom milkshake.

**The Solution:** An online pre-order system that allows customers to order ahead and skip the queue, improving customer satisfaction and restaurant efficiency.

---

## ✨ Features

### For Customers (Patrons)
- ✅ User registration and login
- ✅ Browse available flavours, toppings, and consistencies
- ✅ Build custom milkshake orders (1-10 drinks)
- ✅ Real-time price calculation with VAT
- ✅ Automatic discount calculation for frequent customers
- ✅ Select restaurant location and pickup time
- ✅ Secure payment processing
- ✅ Email confirmation with order details
- ✅ View order history with detailed information
- ✅ Order status tracking

### For Managers
- ✅ Manager dashboard with analytics
- ✅ Manage product lookups (flavours, toppings, consistencies)
- ✅ Configure pricing and system settings
- ✅ Manage discount tiers for loyal customers
- ✅ View comprehensive reports:
  - Order trends by day of week
  - Revenue analysis
  - Top customers
  - Popular items
- ✅ Full audit trail of all system changes

### System Features
- ✅ Responsive design (works on mobile, tablet, and desktop)
- ✅ Real-time form validation
- ✅ Secure authentication with JWT tokens
- ✅ Complete audit logging
- ✅ Email notifications
- ✅ Database-driven configuration

---

## 🛠 Technology Stack

### Frontend
- **React 19.2.0** - UI framework
- **React Router** - Navigation
- **Axios** - API communication
- **CSS3** - Modern styling with gradients and animations

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **PostgreSQL** - Database
- **JWT** - Authentication
- **Bcrypt** - Password hashing
- **Nodemailer** - Email service
- **Stripe** - Payment processing (test mode)

---

## 📦 Prerequisites

Before you begin, ensure you have the following installed on your computer:

### Required Software

1. **Node.js (v18 or higher)**
   - Download from: https://nodejs.org
   - Choose the LTS (Long Term Support) version
   - Verify installation: Open Command Prompt and type `node --version`

2. **PostgreSQL (v14 or higher)**
   - Download from: https://www.postgresql.org/download/
   - During installation, remember the password you set for the `postgres` user
   - Verify installation: Open Command Prompt and type `psql --version`

3. **Git**
   - Download from: https://git-scm.com
   - Verify installation: Open Command Prompt and type `git --version`

4. **A Code Editor (Optional but recommended)**
   - VS Code: https://code.visualstudio.com
   - Or any text editor of your choice

5. **A Gmail Account** (for email notifications)
   - You'll need this to send order confirmation emails

---

## 🚀 Installation Guide

### Step 1: Download the Project

1. Open Command Prompt (Windows) or Terminal (Mac/Linux)
2. Navigate to where you want to store the project:
   ```bash
   cd C:\Users\YourName\Documents
   ```
3. Clone or download the project files to this location

### Step 2: Set Up the Database

1. **Open PostgreSQL Command Line (psql)**
   - On Windows: Search for "SQL Shell (psql)" in Start Menu
   - On Mac/Linux: Open Terminal and type `psql -U postgres`

2. **Enter your PostgreSQL password** when prompted

3. **Create the database:**
   ```sql
   CREATE DATABASE milkyshaky;
   ```

4. **Connect to the database:**
   ```sql
   \c milkyshaky
   ```

5. **Run the schema file:**
   - If you have the `database-schema.sql` file, run:
     ```sql
     \i C:/path/to/database-schema.sql
     ```
   - Replace the path with the actual location of your SQL file

6. **Verify tables were created:**
   ```sql
   \dt
   ```
   You should see tables like `users`, `orders`, `flavours`, etc.

7. **Create a manager account:**
   ```sql
   INSERT INTO users (email, password_hash, first_name, mobile_number, role)
   VALUES ('manager@milkyshaky.co.za', '$2b$10$xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx', 'Admin', '0800000000', 'manager');
   ```

### Step 3: Configure the Backend

1. **Navigate to the backend folder:**
   ```bash
   cd milkyshaky/backend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```
   This will take 2-3 minutes. Wait for it to complete.

3. **Configure environment variables:**
   - Open the `.env` file in the `backend` folder
   - Update these values with your information:
   ```env
   # Database Configuration
   DB_HOST=localhost
   DB_PORT=5432
   DB_NAME=milkyshaky
   DB_USER=postgres
   DB_PASSWORD=YOUR_POSTGRES_PASSWORD_HERE

   # Email Configuration (Gmail)
   EMAIL_HOST=smtp.gmail.com
   EMAIL_PORT=587
   EMAIL_USER=your-email@gmail.com
   EMAIL_PASSWORD=your-gmail-app-password
   EMAIL_FROM=noreply@milkyshaky.co.za
   ```

4. **Get Gmail App Password** (for email notifications):
   - Go to: https://myaccount.google.com/security
   - Enable "2-Step Verification"
   - Search for "App passwords"
   - Create a new app password for "Mail"
   - Copy the 16-character password
   - Paste it in the `.env` file as `EMAIL_PASSWORD`

### Step 4: Configure the Frontend

1. **Navigate to the frontend folder:**
   ```bash
   cd ../frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```
   This will also take 2-3 minutes.

---

## ▶️ Running the Application

You need to run both the backend and frontend simultaneously.

### Option 1: Using Two Command Prompts (Easiest)

**Terminal 1 - Backend:**
```bash
cd C:\path\to\milkyshaky\backend
node server.js
```

You should see:
```
🥤 ================================== 🥤
   Milky Shaky API Server
   Running on port 5000
   Environment: development
🥤 ================================== 🥤
✅ Connected to PostgreSQL database
```

**Terminal 2 - Frontend:**
```bash
cd C:\path\to\milkyshaky\frontend
npm start
```

The browser will automatically open to `http://localhost:3000`

### Option 2: Using VS Code (Recommended)

1. Open the `milkyshaky` folder in VS Code
2. Open the integrated terminal (View → Terminal)
3. Split the terminal (click the split icon)
4. In the left terminal:
   ```bash
   cd backend
   node server.js
   ```
5. In the right terminal:
   ```bash
   cd frontend
   npm start
   ```

---

## 👤 User Guide

### Registration and Login

**For Customers:**

1. **Visit the homepage:** `http://localhost:3000`
2. **Click "Sign Up"**
3. **Fill in your details:**
   - First Name
   - Email Address
   - Mobile Number
   - Password (minimum 6 characters)
4. **Click "Sign Up"** - You'll be automatically logged in

<img width="596" height="742" alt="registration" src="https://github.com/user-attachments/assets/4c99b5af-bc10-4cad-b81f-7a6a82bd0a24" />

**For Managers:**

Use the pre-created manager account:
- Email: `manager@milkyshaky.co.za`
- Password: `Manager123!`

### Placing an Order (Customer)

1. **Click "Order" in the navigation bar**

2. **Select Pickup Details:**
   - Choose a restaurant location
   - Select date and time for pickup (must be in the future)

3. **Build Your Drinks:**
   - Select a Flavour (e.g., Strawberry, Chocolate)
   - Choose a Topping (e.g., Frozen Strawberries, Oreo Crumbs)
   - Pick a Consistency (e.g., Double Thick, Milky)
   - See the price update in real-time

4. **Add More Drinks (Optional):**
   - Click "+ Add Another Drink" (up to 10 drinks)
   - Each drink can be customized differently
  
  <img width="1403" height="357" alt="order" src="https://github.com/user-attachments/assets/b413bcaf-59ed-4948-a7b0-ad255e5f6b79" />

5. **Review Order Summary:**
   - Check subtotal, VAT, and total amount
   - Any applicable discounts will be shown

<img width="1098" height="747" alt="order-detail" src="https://github.com/user-attachments/assets/8e8c9273-7a7b-4aa3-ad30-25d9745fb740" />

6. **Click "Continue to Payment"**
7. **Complete Payment:**
   - Select payment method (Credit Card, Debit Card, or Cash on Pickup)
   - Enter card details if paying by card
   - Click "Pay"

 <img width="596" height="742" alt="registration" src="https://github.com/user-attachments/assets/cb393246-b991-4b5c-8778-8da663f07461" />

8. **Confirmation:**
   - You'll see a success message
   - Check your email for order confirmation
   - You'll be redirected to "My Orders."

### Viewing Orders

<img width="1480" height="357" alt="my-orders" src="https://github.com/user-attachments/assets/cac665fb-c0e5-46cb-bf4d-ba67b4259457" />

1. **Click "My Orders" in the navigation bar**
2. **See all your orders** with status badges:
   - 🟡 PENDING - Order created, awaiting payment
   - 🟢 PAID - Payment successful, being prepared
   - 🔵 PREPARING - Currently being made
   - 🟣 READY - Ready for pickup
   - ⚫ COLLECTED - Order completed
   - 🔴 CANCELLED - Order cancelled

3. **Click on any order** to see full details:
   - All drinks with customizations
   - Pickup location and time
   - Complete pricing breakdown
   - Payment information

---

## 👨‍💼 Manager Guide

### Accessing the Dashboard

1. **Log in as manager** (email: `manager@milkyshaky.co.za`)
2. **Click "Dashboard"** in the navigation bar
3. You'll see two main sections:
   - 📋 Lookup Management
   - 📊 Reports

### Lookup Management

Manage all configurable options for the system:

**1. Flavours Tab:**
- View all available flavours
- Click "+ Add New" to add a flavour
- Enter name and price
- Click "Edit" to modify existing flavours
- Click "Delete" to deactivate (soft delete)

**2. Toppings Tab:**
- Same functionality as Flavours
- Manage all available toppings
- Set individual pricing

**3. Consistencies Tab:**
- Manage drink consistency options
- Set pricing for each option

**4. Config Tab:**
- View system configuration
- Modify:
  - VAT percentage
  - Minimum drinks per order
  - Maximum drinks per order
  - Maximum discount percentage

**5. Discounts Tab:**
- Manage loyalty discount tiers
- Set requirements:
  - Minimum number of orders
  - Minimum drinks per order
  - Discount percentage
- Example: "Bronze tier: 5 orders with 2+ drinks = 5% discount"

<img width="1472" height="697" alt="dashboard-lookups" src="https://github.com/user-attachments/assets/8985566f-c470-49fe-85f3-0aa02e63534c" />

### Reports and Analytics

**Order Trends:**
- See order volumes by day of week
- Identify busiest days
- Plan staffing accordingly

**Top Customers:**
- View highest-spending customers
- See total orders and amount spent
- Identify loyal customers for special offers

**Popular Items:**
- Most ordered flavours
- Most popular toppings
- Most selected consistencies
- Use data for inventory planning

**Revenue Analysis:**
- Daily revenue breakdown
- Total orders and sales
- Growth trends

<img width="1528" height="372" alt="dashboard-reports" src="https://github.com/user-attachments/assets/a72f2dbd-a5d2-4b81-a1c9-4ec231cba108" />

---

## 🔌 API Documentation

### Authentication Endpoints

**POST** `/api/auth/register`
- Register a new user
- Body: `{ email, password, first_name, mobile_number }`
- Returns: User object + JWT token

**POST** `/api/auth/login`
- Login existing user
- Body: `{ email, password }`
- Returns: User object + JWT token

**GET** `/api/auth/me`
- Get current user profile
- Requires: Authentication header
- Returns: User details

### Order Endpoints

**GET** `/api/orders`
- Get all orders for current user
- Requires: Authentication
- Returns: Array of orders

**GET** `/api/orders/:id`
- Get single order details
- Requires: Authentication
- Returns: Order with items

**POST** `/api/orders`
- Create new order
- Requires: Authentication
- Body: `{ restaurant_id, pickup_time, items[] }`
- Returns: Created order

**POST** `/api/orders/:id/pay`
- Process payment for order
- Requires: Authentication
- Body: `{ payment_method, payment_reference }`
- Returns: Payment confirmation + sends email

### Lookup Endpoints

**GET** `/api/lookups/flavours`
- Get all active flavours
- Public endpoint
- Returns: Array of flavours with prices

**GET** `/api/lookups/toppings`
- Get all active toppings
- Public endpoint
- Returns: Array of toppings with prices

**GET** `/api/lookups/consistencies`
- Get all active consistencies
- Public endpoint
- Returns: Array of consistencies with prices

**GET** `/api/lookups/restaurants`
- Get all active restaurants
- Public endpoint
- Returns: Array of restaurant locations

**POST** `/api/lookups/flavours`
- Add new flavour (Manager only)
- Requires: Manager authentication
- Body: `{ name, price }`

**PUT** `/api/lookups/flavours/:id`
- Update flavour (Manager only)
- Requires: Manager authentication
- Body: `{ name, price, is_active }`

**DELETE** `/api/lookups/flavours/:id`
- Deactivate flavour (Manager only)
- Requires: Manager authentication

### Report Endpoints

**GET** `/api/reports/my-orders`
- Get order history for current user
- Requires: Authentication
- Query params: `status, from_date, to_date, limit`

**GET** `/api/reports/trends`
- Get order trends by day of week (Manager only)
- Requires: Manager authentication
- Returns: Order volumes per day

**GET** `/api/reports/popular-items`
- Get most popular items (Manager only)
- Requires: Manager authentication
- Returns: Top flavours, toppings, consistencies

**GET** `/api/reports/customers`
- Get customer statistics (Manager only)
- Requires: Manager authentication
- Returns: Top customers and spending data

---

## 🐛 Troubleshooting

### Backend Won't Start

**Problem:** "Cannot find module" error
- **Solution:** Run `npm install` in the backend folder

**Problem:** "Database connection failed"
- **Solution 1:** Check PostgreSQL is running
- **Solution 2:** Verify credentials in `.env` file
- **Solution 3:** Ensure database `milkyshaky` exists

**Problem:** "Port 5000 already in use"
- **Solution:** Change PORT in `.env` to 5001 or another available port

### Frontend Won't Start

**Problem:** "react-scripts not found"
- **Solution:** Run `npm install` in the frontend folder

**Problem:** Blank white screen
- **Solution 1:** Open browser console (F12) and check for errors
- **Solution 2:** Clear browser cache and localStorage
- **Solution 3:** Ensure backend is running

### Email Not Sending

**Problem:** "Email authentication failed"
- **Solution:** Use Gmail App Password, not a regular password
- **Steps:**
  1. Enable 2-Step Verification on Gmail
  2. Generate App Password
  3. Update `.env` with the 16-character password

**Problem:** Emails go to spam
- **Solution:** This is normal for test environments. Check the spam folder.

### Payment Not Working

**Problem:** Payment fails
- **Solution:** This is a test mode. The payment is simulated.
- Any card details will work in test mode.

### Can't Login as Manager

**Problem:** "Invalid credentials."
- **Solution:** Register a new account, then update the role in the database:
  ```sql
  UPDATE users SET role = 'manager' WHERE email = 'your-email@example.com';
  ```

### Orders Show as Pending Instead of Paid

**Problem:** Status doesn't update after payment
- **Solution:** Check the browser console for errors
- Verify payment endpoint is being called
- Check backend logs for errors

---

## 📧 Support

If you encounter issues not covered in this guide:

1. **Check the browser console** (F12 → Console tab)
2. **Check the backend terminal** for error messages
3. **Verify all environment variables** in `.env`
4. **Ensure PostgreSQL is running**
5. **Make sure both backend and frontend are running**

---

## ✅ Mandatory Requirements Checklist

All assignment requirements have been implemented:

- ✅ **Database:** PostgreSQL with 11 tables
- ✅ **Configurable Fees:** System config table for VAT, min/max drinks, etc.
- ✅ **Lookup Manager:** Complete CRUD interface for all lookups
- ✅ **Full Auditing:** audit_logs table tracks all changes
- ✅ **Confirmation Email:** Sent after successful payment
- ✅ **Payment Gateway:** Stripe integration (test mode)
- ✅ **Two User Profiles:** Patron and Manager roles with different permissions
- ✅ **Final Receipt by Email:** HTML email with complete order details
- ✅ **User/Patron Reports:** Order history with filters
- ✅ **Management Reports:** Trends, revenue, customers, popular items

---

## 🎉 Conclusion

Congratulations! You now have a fully functional online ordering system for Milky Shaky Custom Drinks.

**Key Features:**
- Customers can order custom milkshakes online
- Automatic discount calculation for loyal customers
- Email confirmations with order details
- Real-time order tracking
- Manager dashboard for complete control
- Full audit trail of all system changes

**Built With:**
- Modern React frontend
- RESTful API with Express.js
- PostgreSQL database
- JWT authentication
- Email notifications
- Payment processing
