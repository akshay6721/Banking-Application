## Getting Started

Welcome to the VS Code Java world. Here is a guideline to help you get started to write Java code in Visual Studio Code.

## Folder Structure

The workspace contains two folders by default, where:

- `src`: the folder to maintain sources
- `lib`: the folder to maintain dependencies

Meanwhile, the compiled output files will be generated in the `bin` folder by default.

> If you want to customize the folder structure, open `.vscode/settings.json` and update the related settings there.


## Dependency Management

The `JAVA PROJECTS` view allows you to manage your dependencies. More details can be found [here](https://github.com/microsoft/vscode-java-dependency#manage-dependencies).


# 🏦 Secure Core Banking System (Java & SQL)

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-0078D4?style=for-the-badge&logo=visual%20studio%20code&logoColor=white)

## 📌 Project Overview
The **Secure Core Banking System** is a robust desktop application designed to simulate enterprise-level banking operations. Built using **Java Swing** for the frontend and **MySQL** for the backend, this project demonstrates a full-stack implementation of a financial management system. It features secure user authentication via hashing, real-time transaction processing, and persistent data storage.

## 🚀 Key Features
* **🔐 Secure Authentication:** Implemented **SHA-256 Hashing** to encrypt user passwords, ensuring zero plain-text storage in the database.
* **📊 Live Dashboard:** Dynamic user dashboard showing real-time balance updates after every transaction.
* **💸 Core Operations:** Supports Deposits, Withdrawals, and Balance Inquiries with instant database reflection.
* **🗄️ Data Persistence:** Uses **JDBC (Java Database Connectivity)** to link the Java application with a **MySQL** database.
* **✅ Input Validation:** Robust Regex validation for emails and mobile numbers to prevent invalid data entry.
* **🏗️ MVC Architecture:** Clean separation of concerns between the GUI (View), Logic (Controller), and Database (Model).

## 🛠️ Tech Stack
* **Language:** Java (JDK 17+)
* **GUI Framework:** Java Swing, AWT
* **Database:** MySQL Community Server 8.0
* **Database Connector:** MySQL Connector/J (JDBC Driver)
* **Security:** SHA-256 Cryptographic Hashing
* **Tools:** VS Code, Git, MySQL Workbench

## ⚙️ Setup & Installation

### Step 1: Database Configuration
Open **MySQL Workbench** or your terminal and run the following script to initialize the database:

```sql
CREATE DATABASE IF NOT EXISTS bank_db;
USE bank_db;

CREATE TABLE IF NOT EXISTS users (
    account_id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    mobile VARCHAR(15) NOT NULL,
    password_hash VARCHAR(64) NOT NULL,
    balance DOUBLE DEFAULT 0.0,
    city VARCHAR(50),
    pin VARCHAR(10)
);

-- Insert Default Admin Account (Password: admin123)
INSERT INTO users (first_name, last_name, email, mobile, password_hash, balance, city, pin) 
VALUES ('Admin', 'User', 'admin@zerobank.com', '9999999999', '240be518fabd2724ddb6f04eeb1da5967448d7e831c08c8fa822809f74c720a9', 50000, 'Metropolis', '100001');


### Step 2: Java Project Setup

Clone the repository:

```Bash
git clone [https://github.com/akshay6721/Banking-Application.git](https://github.com/akshay6721/Banking-Application.git)
Open the project in VS Code, Eclipse, or IntelliJ.```

Add the JDBC Driver:

Download mysql-connector-j-8.x.x.jar.

Add it to your projects Referenced Libraries or Dependencies.

### Step 3: Configure Credentials

Open BankUserManualMP.java and find the BankDatabase class. Update the PASS variable with your local MySQL password:

```Java
class BankDatabase {
    static final String DB_URL = "jdbc:mysql://localhost:3306/bank_db"; 
    static final String USER = "root"; 
    static final String PASS = "YOUR_MYSQL_PASSWORD_HERE"; // <--- Update this
}```

## 📸 Usage Guide
Run the Application: Execute the BankUserManualMP.java file.

Login: Use the pre-configured Admin account:

Name: Admin

Password: admin123

Register: Click "New User" to create a fresh account. The system will auto-generate a secure password hash.

Transact: Deposit or Withdraw funds and check your balance securely.

## 🤝 Contributing
Contributions are welcome! Please fork the repository and create a pull request for any feature enhancements or bug fixes.

## 👤 Author
Akshay - Java Developer & Tech Enthusiast