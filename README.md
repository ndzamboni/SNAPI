# SNAPI (Social Network API)

## Description

SNAPI (Social Network API) allows users to interact in a social network by creating and managing users, thoughts (similar to posts), reactions (similar to comments), and friendships. Built using Express.js, MongoDB, and Mongoose, this API supports CRUD operations for users, thoughts, reactions, and friendships. It is designed for scalability with a NoSQL database.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
  - [Users](#users)
  - [Thoughts](#thoughts)
  - [Reactions](#reactions)
  - [Friendships](#friendships)
- [Testing with Insomnia](#testing-with-insomnia)
- [Environment Variables](#environment-variables)
- [Future Enhancements](#future-enhancements)
- [Tech Stack](#tech-stack)
- [License](#license)

## Installation

To install and set up the project locally, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/ndzamboni/snapi.git


2. Navigate to the project directory:
    ```bash
    npm install
    ```

4. Ensure MongoDB is installed and running on your machine. If not, install MongoDB.

## Usage

To start the server, run the following command in the project directory:

    npm start

## Tech Stack

- **Backend**:
  - [Node.js](https://nodejs.org/) - JavaScript runtime for building the backend.
  - [Express.js](https://expressjs.com/) - Web framework for Node.js.
  - [MongoDB](https://www.mongodb.com/) - NoSQL database for storing data.
  - [Mongoose](https://mongoosejs.com/) - ODM for MongoDB, allowing schema-based models.

- **Development Tools**:
  - [Nodemon](https://nodemon.io/) - Automatically restarts the server on file changes.
  - [Insomnia](https://insomnia.rest/) - API testing tool.

- **Future Tech Considerations**:
  - [JWT](https://jwt.io/) - For implementing authentication and authorization.
  - [Passport.js](http://www.passportjs.org/) - Middleware for authentication.
  - [React.js](https://reactjs.org/) - For a future front-end client.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.




