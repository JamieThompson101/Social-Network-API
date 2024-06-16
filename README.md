# Social Network API README

## Overview

The Social Network API is a powerful and flexible API designed for creating and managing social networking platforms. This API provides endpoints for user management, post creation, interactions (likes, comments), and network connections (following, friends).

## Table of Contents

1. [Getting Started](#getting-started)
2. [Authentication](#authentication)
3. [Endpoints](#endpoints)
    - [Users](#users)
    - [Posts](#posts)
    - [Interactions](#interactions)
    - [Connections](#connections)
4. [Error Handling](#error-handling)
5. [Rate Limiting](#rate-limiting)
6. [Examples](#examples)
7. [License](#license)

## Getting Started

### Prerequisites

- Node.js
- npm

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

### Running the API

To start the server, run:
```sh
npm start
```

The API will be available at `http://localhost:3000`.

## Authentication

Authentication is required for most endpoints. This API uses JSON Web Tokens (JWT) for authentication.

### Register

`POST /api/auth/register`

**Request:**
```json
{
  "username": "exampleUser",
  "email": "user@example.com",
  "password": "examplePassword"
}
```

**Response:**
```json
{
  "message": "User registered successfully."
}
```

### Login

`POST /api/auth/login`

**Request:**
```json
{
  "email": "user@example.com",
  "password": "examplePassword"
}
```

**Response:**
```json
{
  "token": "your.jwt.token.here"
}
```

Include this token in the `Authorization` header for authenticated requests:
```http
Authorization: Bearer your.jwt.token.here
```

## Endpoints

### Users

#### Get User Profile

`GET /api/users/:id`

**Response:**
```json
{
  "id": "userId",
  "username": "exampleUser",
  "email": "user@example.com",
  "profile": {
    "bio": "This is an example bio.",
    "location": "Example City"
  }
}
```

### Posts

#### Create Post

`POST /api/posts`

**Request:**
```json
{
  "content": "This is a new post!"
}
```

**Response:**
```json
{
  "id": "postId",
  "content": "This is a new post!",
  "authorId": "userId",
  "createdAt": "2023-01-01T00:00:00.000Z"
}
```

#### Get Posts

`GET /api/posts`

**Response:**
```json
[
  {
    "id": "postId",
    "content": "This is a new post!",
    "authorId": "userId",
    "createdAt": "2023-01-01T00:00:00.000Z"
  },
  ...
]
```

### Interactions

#### Like Post

`POST /api/posts/:id/like`

**Response:**
```json
{
  "message": "Post liked successfully."
}
```

#### Comment on Post

`POST /api/posts/:id/comments`

**Request:**
```json
{
  "content": "This is a comment."
}
```

**Response:**
```json
{
  "id": "commentId",
  "content": "This is a comment.",
  "authorId": "userId",
  "postId": "postId",
  "createdAt": "2023-01-01T00:00:00.000Z"
}
```

### Connections

#### Follow User

`POST /api/users/:id/follow`

**Response:**
```json
{
  "message": "User followed successfully."
}
```

#### Unfollow User

`POST /api/users/:id/unfollow`

**Response:**
```json
{
  "message": "User unfollowed successfully."
}
```

## Error Handling

Errors are returned in the following format:

```json
{
  "error": "Error message here"
}
```

## Rate Limiting

To prevent abuse, the API implements rate limiting. Each user is allowed 1000 requests per hour. If you exceed this limit, you will receive a `429 Too Many Requests` response.

## Examples

### Fetching User Data

```sh
curl -H "Authorization: Bearer your.jwt.token.here" http://localhost:3000/api/users/123
```

### Creating a Post

```sh
curl -X POST -H "Authorization: Bearer your.jwt.token.here" -H "Content-Type: application/json" -d '{"content":"This is a new post!"}' http://localhost:3000/api/posts
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Credits

A special shoutout to chat gpt and freecodecamp for making coding easy.

## Questions

If you have any questions or concerns, please contact me at my [github](https://github.com/JamieThompson101)
