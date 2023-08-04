# Spring Boot JWT Authentication and Authorization

This project demonstrates how to implement authentication and authorization using JSON Web Tokens (JWT) in a Spring Boot application. JSON Web Tokens are a popular method for securely transmitting information between parties as a JSON object. This project showcases how to generate and validate JWT tokens for user authentication and how to enforce authorization rules based on user roles.

## Features
- User registration and authentication using JWT.

- Role-based authorization for protecting endpoints.

- JSON Web Token generation and validation.
  
- Password hashing for secure storage of user passwords.

## Installation
Clone this repository to your local machine using Git:

```bash

git clone git@github.com:abhinavsingh3281/Authentication-Spring-Boot.git

Open the project in your favorite IDE (e.g., IntelliJ, Eclipse, or Visual Studio Code).

Configure the database settings in the application.properties file to connect to your desired database:

properties

spring.datasource.url=jdbc:mysql://localhost:3306/mydatabase

spring.datasource.username=username

spring.datasource.password=password

Build and run the application.

```

## Usage

Register a new user by sending a POST request to **/api/v1/user**

With JSON data containing email, password, and role fields. The role can be **CUSTOMER / VENDOR / COLLECTOR**.

```bash
curl -X 'POST' \
  'http://localhost:8083/api/v1/user' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "firstName": "Abhinav",
  "lastName": "Singh",
  "email": "abhi1@gmail.com",
  "role": {
    "name": "CUSTOMER"
  },
  "mobileNo": "9090909090",
  "password": "123456",
  "matchingPassword": "123456",
  "address1": "12 sec-1",
  "city": "HSR",
  "state": "HRY",
  "pinCode": "123456"
}'
```

Authenticate a user by sending a POST request to **/api/v1/sign-in**

With JSON data containing email and password fields. The response will contain a JWT token / Refresh Token if the authentication is successful.

```bash

curl -X 'POST' \
  'http://localhost:8083/api/v1/sign-in' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "email": "abhi1@gmail.com",
  "password": "123456"
}'

```

Use the obtained JWT token in the Authorization header for protected endpoints. The Authorization header should be in the format: 

**Bearer <JWT-token>**
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9....

Access protected endpoints based on user roles. For example, sending a GET request to /api/v1/profile/edit will update details of user If token is present and user has access to the API then only details will be updated. Otherwise, it will return a 403 Forbidden error.

## Security Considerations

- Ensure to use HTTPS in production to secure the transmission of JWT tokens.
  
- Do not store sensitive information in JWT tokens.

- Implement token expiration and refresh mechanisms to enhance security.

- Use strong and unique secrets for signing JWT tokens.

- Use password hashing with a strong hashing algorithm like BCrypt.

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request.

## License

[MIT](https://choosealicense.com/licenses/mit/)


## Badges

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)

[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)

[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)


## Screenshots

- SignUp Request
  
<img width="1412" alt="Screenshot 2023-08-05 at 12 28 10 AM" src="https://github.com/abhinavsingh3281/Authentication-Spring-Boot/assets/52294538/98282db0-829d-4cc7-b5d8-78f3edb0c566">


- SignUp Response

<img width="1389" alt="Screenshot 2023-08-05 at 12 28 34 AM" src="https://github.com/abhinavsingh3281/Authentication-Spring-Boot/assets/52294538/6977072f-1024-4bb9-967a-d161b181e65b">

- SignIn Request
  
  <img width="1426" alt="Screenshot 2023-08-05 at 12 36 27 AM" src="https://github.com/abhinavsingh3281/Authentication-Spring-Boot/assets/52294538/73ca7e85-e5b7-4603-8295-8a6854232ec6">

- SignIn Response
  
<img width="1420" alt="Screenshot 2023-08-05 at 12 36 35 AM" src="https://github.com/abhinavsingh3281/Authentication-Spring-Boot/assets/52294538/924a6c09-295d-4a83-adbb-10d4fe9df6b7">

- Reset Password Request

<img width="1425" alt="Screenshot 2023-08-05 at 12 52 52 AM" src="https://github.com/abhinavsingh3281/Authentication-Spring-Boot/assets/52294538/e26a44e7-fd05-4d97-8c5c-769eaff43421">

- Reset Password Response
  
<img width="1429" alt="Screenshot 2023-08-05 at 12 52 59 AM" src="https://github.com/abhinavsingh3281/Authentication-Spring-Boot/assets/52294538/5edb97b7-149d-441e-8ad0-28e975ca6594">

- Reset Password Email
  
<img width="623" alt="Screenshot 2023-08-05 at 12 52 40 AM" src="https://github.com/abhinavsingh3281/Authentication-Spring-Boot/assets/52294538/4b9ac571-5086-4526-8fa3-fd825e420cc7">
  

## 🚀 About Me

👋 Hi, I’m @abhinavsingh3281 Software Engineer @ Tiket

👀 I’m interested in learning new tech-related stuff.

🌱 I’m currently learning Android Development using Java, Rest API in Spring, and Golang.

📫 How to reach me ... LinkedIn - [https://www.linkedin.com/in/abhinavvsingh/](https://www.linkedin.com/in/singhabhinavv/)


## Support

For support, email abhinavhissar@gmail.com.

