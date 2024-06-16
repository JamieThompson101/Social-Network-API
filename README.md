# Social Network API README

## Overview

This Social Network API utilizes Express.js for routing, a MongoDB database, and the Mongoose ODM. Through this, users are able to share their thoughts, react to friends' thoughts, and create a friends list.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Rate Limiting](#rate-limiting)
3. [License](#license)
4. [Questions](#questions)

## Getting Started

### Prerequisites

- Node.js
- npm
- mongoDB
- moment

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/social-network-api.git
   ```
2. Navigate to the project directory:
   ```sh
   cd social-network-api
   ```
3. Install the dependencies:
   ```sh
   npm install
   ```
   ```sh
   npm install moment
   ```
   ```sh
   mongosh
   ```

### Running the API

To start the server, run:
```sh
npm start
```

The API will be available at `http://localhost:3001`.

## Authentication

Authentication is required for most endpoints. This API uses JSON Web Tokens (JWT) for authentication.

## Rate Limiting

To prevent abuse, the API implements rate limiting. Each user is allowed 1000 requests per hour. If you exceed this limit, you will receive a `429 Too Many Requests` response.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Credits

A special shoutout to chat gpt and freecodecamp for making coding easy.

## Questions

If you have any questions or concerns, please contact me at my [github](https://github.com/JamieThompson101)
