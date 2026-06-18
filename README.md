Here is a **simple and beginner-friendly README section**:

********Bank Transaction System ************

## Base URL

```text
http://localhost:3000
```

## Authentication

Most APIs require a JWT token in the request header:

```text
Authorization: Bearer <your_token>
```

---

## 1. User Authentication

### Register User

* **POST** `/api/auth/register`

**Request Body**

```json
{
  "email": "user@example.com",
  "password": "password123",
  "name": "John Doe"
}
```

### Login

* **POST** `/api/auth/login`

**Request Body**

```json
{
  "email": "user@example.com",
  "password": "password123"
}
```

**Response**

Returns user details and a JWT token.

### Logout

* **POST** `/api/auth/logout`

**Header**

```text
Authorization: Bearer <token>
```

---

## 2. Account APIs

### Create Account

* **POST** `/api/accounts`

Creates a new account for the logged-in user.


### Get Account Balance

* **GET** `/api/accounts/balance/:accountId`

Returns the current balance of a specific account.

---

## 3. Transaction APIs

### Transfer Money

* **POST** `/api/transactions`

**Request Body**

```json
{
  "fromAccount": "sender_account_id",
  "toAccount": "receiver_account_id",
  "amount": 500,
  "idempotencyKey": "unique-key"
}
```

Transfers money from one account to another.

### Add Initial Funds

* **POST** `/api/transactions/system/initial-funds`

**Request Body**

```json
{
  "toAccount": "your_account_id",
  "amount": 1000,
  "idempotencyKey": "unique-key"
}
```

Adds money from the system account to your account. Useful for testing.

---

## Run Locally

### 1. Clone the project

```bash
git clone <repository-url>
```

### 2. Install dependencies

```bash
npm install
```

### 3. Create `.env` file

Add your environment variables in the `.env` file.

### 4. Start the server

```bash
npm run dev
```

The server will run at:

```text
http://localhost:3000
```


