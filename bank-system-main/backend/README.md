# Banking API

This project is a RESTful API for a banking system. It provides a comprehensive set of features for managing bank accounts and users. The API is built with Node.js and Express.js, and uses PostgreSQL for data storage.

The project has been updated to use ES6 import/export syntax.

## Features

### Account Management

- **Create a new account:** Add a new account to the system with a unique account number.
- **Update an existing account:** Modify the details of an existing account, such as the account name, balance, account type, currency, and status.
- **Retrieve an account by account number:** Fetch the details of a specific account using its unique account number.
- **Retrieve all accounts:** Get a list of all accounts in the system.
- **Delete an account:** Remove an account from the system.

### User Management

- **Create a new user:** Add a new user to the system. The user's password is hashed using bcrypt for security. An address can also be added for the user.
- **Update an existing user:** Modify the details of an existing user, including their associated address. If a new password is provided, it is hashed before being stored.
- **Retrieve a user by ID:** Fetch the details of a specific user using their ID, including their associated address.
- **Retrieve all users:** Get a list of all users in the system, including their associated addresses. Supports pagination to limit the number of users returned in a single request.
- **Delete a user:** Remove a user from the system, including their associated address.

### Transaction Management

- **Create a new transaction:** Add a new transaction to the system. The transaction can be a deposit, withdrawal, or transfer.
- **Retrieve all transactions:** Get a list of all transactions in the system.
- **Retrieve a transaction by ID:** Fetch the details of a specific transaction using its ID.
- **Retrieve transactions by account number:** Fetch all transactions for a specific account using the account number.
- **Retrieve transactions by user ID:** Fetch all transactions for a specific user using the user ID.
- **Reverse a transaction:** Reverse a transfer transaction.

## Technologies Used

- **Node.js:** A JavaScript runtime built on Chrome's V8 JavaScript engine.
- **Express.js:** A fast, unopinionated, minimalist web framework for Node.js.
- **PostgreSQL:** A powerful, open source object-relational database system.
- **Sequelize ORM:** A promise-based Node.js ORM for Postgres, MySQL, MariaDB, SQLite and Microsoft SQL Server. It supports the dialects PostgreSQL, MySQL, SQLite and MSSQL and features solid transaction support, relations, read replication and more.
- **bcrypt:** A library to help you hash passwords.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

- Node.js
- PostgreSQL

### Installation

1. Clone the repository: `git clone https://github.com/Ellyian/my-bank-api.git`
2. Navigate into the project directory: `cd my-bank-api`
3. Install the dependencies: `npm install`
4. Create a `.env` file and add your database configuration. See `.env.example` for a sample configuration.
5. Run the database migrations: `npx sequelize-cli db:migrate`
6. Start the server: `npm run dev`

## API Endpoints

### Account Endpoints

- `GET /api/accounts`: Retrieve all accounts
- `GET /api/accounts/:accountNumber`: Retrieve an account by account number
- `POST /api/accounts`: Create a new account
- `PUT /api/accounts/:accountNumber`: Update an account
- `DELETE /api/accounts/:accountNumber`: Delete an account
- `GET /api/accounts/name/:name`: Retrieve accounts by name
- `PUT /api/accounts/:accountNumber/activate`: Activate an account
- `GET /api/accounts/type/:accountType`: Retrieve accounts by type

### User Endpoints

- `GET /api/users`: Retrieve all users
- `GET /api/users/:id`: Retrieve a user by ID
- `POST /api/users`: Create a new user
- `PUT /api/users/:id`: Update a user
- `DELETE /api/users/:id`: Delete a user

### Transaction Endpoints

- `POST /api/transactions`: Create a new transaction
- `GET /api/transactions`: Retrieve all transactions
- `GET /api/transactions/:id`: Retrieve a transaction by ID
- `POST /api/transactions/:id/reverse`: Reverse a transaction
- `GET /api/transactions/account/:accountId`: Retrieve transactions by account ID
- `GET /api/transactions/user/:userId`: Retrieve transactions by user ID
- `GET /api/transactions/accountNumber/:accountNumber`: Retrieve transactions by account number

## Running Tests

To run the tests, use the following command: `npm test`

## Contributing

Contributions are welcome! If you want to contribute to this project, please create a pull request. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is the property of Nicanor Kyamba. All rights reserved.
