# Node.js Email Verification Project

## Overview

This Node.js project is designed to handle user signups and send verification emails using Nodemailer. Upon successful signup through the endpoint `http://localhost:3000/auth/signup`, a verification email containing a URL is sent to the user. The user can click on the URL to verify their account.

## Features

- User signup endpoint (`/auth/signup`) for account creation.
- Nodemailer integration to send verification emails.
- Token-based email verification for enhanced security.

## Prerequisites

Make sure you have the following installed before running the project:

- Node.js
- npm (Node Package Manager)

  Create a `.env` file with below

  ```sh
  PORT=<server port>
  MONGODB_URI=<mangodb cluster URL>
  JWT_SECRET=<any random secret key>
  ```

## Getting Started

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/node-email-verification.git
   ```

   Copy paste the `.env` file created above in this project

2. Setup Project
   ```bash
   npm install
   ```
3. Start server
   ```bash
   node app.js
   ```

## 1.User Signup API Endpoint

### Overview

This API endpoint is responsible for user registration and account creation. Users can sign up by sending a POST request to `http://localhost:3000/auth/signup` with the required information in the request body.

### Endpoint Details

- **Method:** POST
- **Endpoint:** `/auth/signup`

### Request

#### Body Parameters

- **fullname** (string): The full name of the user.
- **username** (string): The email address or username for the user's account.
- **password** (string): The chosen password for the user's account.
- **confirmPassword** (string): Confirmation of the chosen password.

#### Example Request Body

```json
{
  "fullname": "String",
  "username": "String",
  "password": "String",
  "confirmPassword": "String"
}
```

## 2.User Sign-In API Endpoint

### Overview

This API endpoint handles user authentication. Users can sign in by sending a POST request to `http://localhost:3000/auth/signin` with their username and password in the request body.

### Endpoint Details

- **Method:** POST
- **Endpoint:** `/auth/signin`

### Request

#### Body Parameters

- **username** (string): The email address or username associated with the user's account.
- **password** (string): The user's password.

#### Example Request Body

```json
{
  "username": "string",
  "password": "string"
}
```

## 3.User Information Retrieval API Endpoint

### Overview

This API endpoint allows fetching user information based on the provided username. Authentication is required through either a Bearer token or Basic Authentication.

Bearer token will be generated in response once you access the [Signin](#User-Sign-In-API-Endpoint).

### Endpoint Details

- **Method:** GET
- **Endpoint:** `/users/{username}`

### Authentication

Access to this endpoint requires authentication. You can provide authentication using either of the following methods:

#### Bearer Token

Include a valid Bearer token in the Authorization header:

```http
Authorization: Bearer your_access_token
```

If you are using postman, go to Authorization and select the Bearer token in type.

## 4.User Information Update API Endpoint

### Overview

This API endpoint allows updating user information based on the provided username. Authentication is required through either a Bearer token or Basic Authentication.

### Endpoint Details

- **Method:** PUT
- **Endpoint:** `/users/{username}`

### Authentication

Access to this endpoint requires authentication. You can provide authentication using either of the following methods:

#### Bearer Token

Include a valid Bearer token in the Authorization header:

```http
Authorization: Bearer your_access_token
```

## 5.User Deletion API Endpoint

### Overview

This API endpoint allows deleting a user based on the provided username. Authentication is required through either a Bearer token or Basic Authentication.

### Endpoint Details

- **Method:** DELETE
- **Endpoint:** `/users/{username}`

### Authentication

Access to this endpoint requires authentication. You can provide authentication using either of the following methods:

#### Bearer Token

Include a valid Bearer token in the Authorization header:

```http
Authorization: Bearer your_access_token
```

## 6.All Users Retrieval API Endpoint

### Overview

This API endpoint allows fetching information for all users. Authentication is required through either a Bearer token or Basic Authentication.

### Endpoint Details

- **Method:** GET
- **Endpoint:** `/users`

### Authentication

Access to this endpoint requires authentication. You can provide authentication using either of the following methods:

#### Bearer Token

Include a valid Bearer token in the Authorization header:

```http
Authorization: Bearer your_access_token
```
