# DevLink API

DevLink is a REST API for a developer networking platform. It lets users create developer profiles, share short posts, connect with other developers, and react to posts. The project is built with Node.js, Express, MongoDB, and Mongoose.

## Getting Started

### Prerequisites

- Node.js and npm
- MongoDB running locally, or a MongoDB connection URI

### Install and run

1. Clone or download this repository, then open a terminal in the project directory.
2. Install the dependencies:

   ```sh
   npm install
   ```

3. Start MongoDB. By default, DevLink connects to `mongodb://127.0.0.1:27017/devlink`.
4. Start the API in development mode:

   ```sh
   npm run dev
   ```

   Or run it without the development watcher:

   ```sh
   npm start
   ```

The server starts at `http://localhost:3001` once it connects to MongoDB. Set `MONGODB_URI` to use a different database URI, or set `PORT` to change the server port.

## Try the API

Use an API client such as Insomnia or Postman. All routes are JSON endpoints under `/api`.

| Method | Endpoint                                                 | Description                                      |
| ------ | -------------------------------------------------------- | ------------------------------------------------ |
| GET    | `/api/developers`                                        | List developers                                  |
| GET    | `/api/developers/:developerId`                           | Get a developer, including posts and connections |
| POST   | `/api/developers`                                        | Create a developer                               |
| PUT    | `/api/developers/:developerId`                           | Update a developer                               |
| DELETE | `/api/developers/:developerId`                           | Delete a developer                               |
| POST   | `/api/developers/:developerId/connections/:connectionId` | Add a connection                                 |
| DELETE | `/api/developers/:developerId/connections/:connectionId` | Remove a connection                              |
| GET    | `/api/posts`                                             | List posts, newest first                         |
| GET    | `/api/posts/:postId`                                     | Get a post                                       |
| POST   | `/api/posts`                                             | Create a post                                    |
| PUT    | `/api/posts/:postId`                                     | Update a post                                    |
| DELETE | `/api/posts/:postId`                                     | Delete a post                                    |
| POST   | `/api/posts/:postId/reactions`                           | Add a reaction                                   |
| DELETE | `/api/posts/:postId/reactions/:reactionId`               | Remove a reaction                                |

### Example: create a developer

```http
POST /api/developers
Content-Type: application/json
```

```json
{
  "username": "ada",
  "email": "ada@devlink.io",
  "headline": "Full-Stack Developer",
  "skills": ["JavaScript", "MongoDB", "React"]
}
```

## Project Structure

```text
config/       MongoDB connection
controllers/  Developer and post request handlers
models/       Mongoose models and schemas
routes/       API route definitions
server.js     Express application entry point
```

## Learning Objectives

By completing this project, students will demonstrate:

- Mongoose schema modeling
- Subdocuments
- References and population
- Virtual fields
- CRUD architecture
- Proper error handling
- RESTful API design

---

## DevLink v1.0 Philosophy

Keep it simple.
Keep it professional.
Ship working software.

---
