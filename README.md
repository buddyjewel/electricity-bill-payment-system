# Electricity Bill Payment System

## Project Overview

The Electricity Bill Payment System is a web-based application designed to simplify the process of managing and paying electricity bills. Its primary purpose is to provide users with a seamless experience for bill creation, payment processing, and wallet management while offering utility companies efficient tools for managing customer accounts.

## Key Features:

- Bill Creation: Users can easily create and manage their electricity bills with user-friendly interfaces.
- Payment Processing: Secure payment gateway integration allows users to make payments safely and conveniently.
- Wallet Management: Users can maintain a digital wallet to manage funds for bill payments and track their balances.
- Event Notifications: Users receive timely notifications for key events such as bill generation, payment confirmations, and wallet updates.

## Setup Instructions

To set up and run the Electricity Bill Payment System, follow these steps:

## Prerequisites

- Node.js (v14 or higher)
- NPM (Node Package Manager)
- A code editor (e.g., Visual Studio Code)
- MongoDB (for database management)
- Postman (for API testing)

## Step-by-Step Instructions

1. Clone the Repository:

   ```bash
   git clone https://github.com/yourusername/electricity-bill-payment-system.git
   cd electricity-bill-payment-system
   ```

2. Install Dependencies:

Make sure you are in the project directory and run:

```bash
npm install
```

3. Set Up Environment Variables:

Create a `.env` file in the root directory and add the following configurations:

```
PORT=3000
DB_URI=mongodb://localhost:27017/electricity-bill
PAYMENT_GATEWAY_KEY=your_payment_gateway_key
```

4. Start the MongoDB Service:

Ensure your MongoDB service is running. You can start it using:\

```bash
mongod
```

5. Start the Server:

Start the application with the following command:

```bash
npm start
```

6. Access the Application:

Open your web browser and navigate to `http://localhost:3000` to view the application.

7. API Testing (Optional):

Use Postman to test the API endpoints:

- Create Bill: `POST /api/bills` (Body: `{ "amount": 100, "dueDate": "2024-12-01", "customerId": "12345" }`)
- Process Payment: `POST /api/payments` (Body: `{ "billId": "bill_id", "amount": 100 }`)
- Manage Wallet: `GET /api/wallet` (Retrieves current wallet balance)

## Event Flow Explanation

The Electricity Bill Payment System employs an event-driven approach to enhance user interaction and streamline operations. Here’s how the key events work:

1. Bill Created:

   - When a user submits a request to create a bill, the system triggers the "bill created" event.
   - This event activates the notification system, sending an alert to the user confirming that the bill has been successfully created.

2. Payment Initiated:

   - When the user initiates a payment for their bill, it triggers the "payment initiated" event.
   - The system begins processing the payment, interacting with the payment gateway.

3. Payment Completed:

   - Once the payment is successfully processed, the "payment completed" event is triggered.
   - Users receive a notification confirming the successful payment, and the bill status is updated to "paid".

4. Wallet Updated:

   - If a user adds funds to their wallet, the "wallet updated" event is triggered.
   - This event updates the user's wallet balance and sends a notification confirming the update.
