# 🏦 Python Bank Management System (MySQL + SMTP)

A fully functional **Banking System** built in Python that connects to a **MySQL database** for secure data storage and uses **Gmail SMTP** for OTP-based email verification during registration.

This project simulates a real-world banking environment with features for **users** and **admins**, including balance management, transactions, and user controls.

## Features

### User Panel
- Registration with OTP verification (email-based)
- Automatic Account Number Generation
- Deposit and Withdrawal functionality
- Transaction History tracking
- View current balance
- Secure login with PIN authentication

### Admin Panel
- View all registered users
- View all transactions
- Delete users
- Search user by Account Number
- Admin login with secure PIN

## Database Structure (MySQL)

**Database:** `bank_system`

**Tables:**

### `users`
| Field | Type | Description |
|-------|------|-------------|
| user_id | INT (PK, AUTO_INCREMENT) | Unique User ID |
| Account_no | VARCHAR | Generated Account Number |
| username | VARCHAR | User’s Name |
| email | VARCHAR | Registered Email |
| pin | VARCHAR | User’s PIN |
| balance | FLOAT | Current Balance |

### `transactions`
| Field | Type | Description |
|-------|------|-------------|
| trans_id | INT (PK, AUTO_INCREMENT) | Transaction ID |
| user_id | INT (FK) | Linked User |
| trans_type | ENUM('deposit','withdraw') | Transaction Type |
| amount | FLOAT | Amount |
| trans_date | TIMESTAMP | Date & Time |

### `admin`
| Field | Type | Description |
|-------|------|-------------|
| admin_id | INT (PK, AUTO_INCREMENT) | Admin ID |
| username | VARCHAR | Admin Username |
| password | VARCHAR | Admin PIN |

---

## Setup Instructions

### Install Dependencies
```bash
pip install mysql-connector-python
```

### Create MySQL Database
Run the script — it automatically creates a database named `bank_system`.

### Configure SMTP
Edit the following section with your Gmail and App Password:
```python
sender_email = "your_email@gmail.com"
sender_password = "your_app_password"
```
Use a Gmail App Password, not your normal password.

### Run the Program
```bash
python bank_system.py
```

---

## Highlights
- Uses **Gmail SMTP** for real-time OTP validation  
- Proper **transaction logging** and **rollback on error**  
- **Secure password inputs** using `getpass`  
- Clean **menu-driven interface**  

---

## Example Flow

```
====== PYTHON BANK SYSTEM ======
1. Register
2. Login
3. Admin Login
4. Exit
```

✅ Register with email → OTP verification → Account created  
✅ Login → Deposit/Withdraw → View balance & history  
✅ Admin can view all users & transactions  

---

## Author
**Ritik Vishwakarma**  
Email: ritikvishwakarma6595@gmail.com  
Project Type: Python CLI + MySQL + SMTP  
