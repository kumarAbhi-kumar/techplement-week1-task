# E-Commerce Store with NodeJS

This is an Express service that provides authorization functionality and includes separate folders for users and products.
It also uses Sequelize ORM with SQLite as the database, along with the JSON Web Token (JWT) and AJV libraries.

## Project Structure
 - `index.js`: The main entry point of the application.
 - `config.js`: Contains configuration files for the application.
 - `authorization`
   - `controllers`: Controller files for authentication endpoints.
   - `schemas`: JSON Schemas against which the body of various routes will be validated.
   - `routes.js`: Registers all the authentication routes.
 - `users`
   - `controllers`: Controller files for user master CRUD endpoints.
   - `schemas`: JSON Schemas against which the body of various routes will be validated.
   - `routes.js`: Registers all the user CRUD routes.
 - `common`
   - `middlewares`: Various middlewares that can be used in various routes like (isAuthenticated, CheckPermissions etc.)
   - `models`: Sequelise models for the Product and User Tables
 - `storage`: Local storage, that stores all the SQLite tables.

## Prerequisites
1. NodeJS 
2. NPM 

## Installation
1. Navigate to the project directory: `cd e-commerce-service`
2. Install the dependencies: `npm install`

## Usage

To start the service, run the following command:
```shell
npm start
```

Signup Command:
```shell
localhost:3000/signup (POST)
```
- `Payload`:
  - {
      "firstName": "Arvind",
      "lastName": "Admin",
      "email": "kasonu876@gmail.com",
      "username": "arvindkalra-admin",
      "password": "arvindkalra-admin",
      "role": "admin",
      "age": 18
    }

Login command:
```shell
localhost:3000/login (POST)
```
- `Payload`:
  - {
      "username": "",
      "password": ""
    }

View all users:
Login command:
```shell
localhost:3000/user/ (PATCH)
```

## License
This project is licensed under the MIT License.




