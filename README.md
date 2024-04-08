# Express & NodeJS Login, SignUp and Update User Profile API

This is an Express service that provides authorization functionality and includes separate folders for users.
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
   - `models`: Sequelise models for the User Tables
 - `storage`: Local storage, that stores all the SQLite tables.

## Prerequisites
1. NodeJS 
2. NPM 

## Installation
1. Navigate to the project directory: `cd techplement-week1-task`
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
  - { <br>
      "firstName": "Kumar", <br>
      "lastName": "Abhishek", <br>
      "email": "fabiamkumar@gmail.com", <br>
      "username": "kumar-admin", <br>
      "password": "kumar-admin", <br>
      "role": "admin", <br>
      "age": 23 <br>
    }

Login command:
```shell
localhost:3000/login (POST)
```
- `Payload`:
  - { <br>
      "username": "", <br>
      "password": "" <br>
    }

View all users:
```shell
localhost:3000/user/all/ (PATCH)
```
Update User:
```shell
localhost:3000/user (PATCH)
```
- *provide auth token in bearers
- `Payload`:
- { <br>
    "firstName": "Kumar", <br>
    "lastName": "Abhishek", <br>
    "age": 24 <br>
- }
