# Online Payment Application with AI-Powered Fraud Detection

## Overview

This project is an **Online Payment Application** with integrated **AI-powered fraud detection** using the `XGBoost` model. The application allows users to register, initiate transactions, and manage their profiles while monitoring for potentially fraudulent activities. Fraud detection is implemented using a machine learning model to analyze transaction data and flag suspicious transactions.

## Features

1. **User Registration & Login**: Secure user authentication and profile management.
2. **Transaction Management**: Users can create and view transaction histories.
3. **AI-Powered Fraud Detection**: Fraud detection is integrated using `XGBoost`, which flags suspicious transactions based on historical data.
4. **Fraud Alerts**: Users are notified when a transaction is detected as fraudulent.
5. **Scalable Backend**: The backend is built using Spring Boot, with Hibernate for ORM and PostgreSQL for data storage.
6. **Responsive Frontend**: A ReactJS frontend that allows users to interact with the application smoothly.

## Technology Stack

### Frontend:
- **ReactJS**: A powerful library for building user interfaces.
- **Axios**: For making HTTP requests to the backend.
- **Bootstrap**: For responsive design and layout.

### Backend:
- **Spring Boot**: Backend framework for building RESTful services.
- **Hibernate**: ORM framework for managing the database.
- **MySQL/PostgreSQL**: Relational database for storing user and transaction data.

### Machine Learning:
- **Python & XGBoost**: Used for training and deploying the fraud detection model.
- **Pickle**: To save and load the trained model.

## Project Structure

```bash
/payment-app
│
├── /frontend                  # ReactJS frontend
│   ├── /public
│   ├── /src
│   │   ├── /components        # Reusable UI components
│   │   ├── /pages             # Application pages (Login, Dashboard, etc.)
│   │   ├── /services          # Axios API service calls
│   │   └── App.js             # Main React app component
│   ├── package.json
│   └── README.md              # Frontend specific README
│
├── /backend                   # Spring Boot backend
│   ├── /src
│   │   ├── /main
│   │   │   ├── /java
│   │   │   │   └── /com
│   │   │   │       └── /paymentapp
│   │   │   │           ├── /controller     # API endpoints
│   │   │   │           ├── /model          # Entity models for database
│   │   │   │           ├── /repository     # Database interaction
│   │   │   │           ├── /service        # Business logic
│   │   │   │           └── /dto            # Data Transfer Objects
│   │   │   └── /resources
│   │   │       └── application.properties  # Configuration properties
│   ├── pom.xml
│   └── README.md              # Backend specific README
│
└── /ml-model                  # Machine Learning model
    ├── model.py               # Python script for training the model
    ├── fraud_detection_model.pkl  # Serialized ML model
    ├── requirements.txt       # Python dependencies
    └── README.md              # Machine Learning model README
```

## Setup Instructions

### 1. Frontend Setup

Navigate to the `frontend` directory and install the required dependencies:

```bash
cd frontend
npm install
```

Run the frontend development server:

```bash
npm start
```

The application will be available at `http://localhost:3000`.

### 2. Backend Setup

Navigate to the `backend` directory and ensure all dependencies are installed:

```bash
cd backend
mvn clean install
```

Configure the database in `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/payment_app
spring.datasource.username=root
spring.datasource.password=password
```

Run the Spring Boot backend:

```bash
mvn spring-boot:run
```

The backend API will be available at `http://localhost:8080/api`.

### 3. Machine Learning Model Setup

Navigate to the `ml-model` directory:

```bash
cd ml-model
pip install -r requirements.txt
```

Train the fraud detection model (if needed):

```bash
python model.py
```

Alternatively, the pretrained model `fraud_detection_model.pkl` can be used directly.

## Key API Endpoints

1. **User Registration**: `POST /api/users/register`
2. **User Login**: `POST /api/auth/login`
3. **Create Transaction**: `POST /api/transactions/create`
4. **Get User Transactions**: `GET /api/transactions/{userId}`
