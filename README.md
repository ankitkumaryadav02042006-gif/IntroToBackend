# Intro to Backend Web Development 🚀

A full-featured Node.js, Express, and MongoDB backend application featuring MVC architecture, user authentication with bcrypt, and complete CRUD operations.

Built as part of the backend development tutorial by Shivani, configured and maintained by [Ankit Kumar Yadav](https://github.com/ankitkumaryadav02042006-gif).

---

## 🛠 Tech Stack

- **Runtime Environment:** [Node.js](https://nodejs.org/) (ES Modules)
- **Web Framework:** [Express.js](https://expressjs.com/) (v5)
- **Database & ODM:** [MongoDB Atlas](https://www.mongodb.com/atlas) with [Mongoose](https://mongoosejs.com/) (v8)
- **Authentication & Security:** [bcrypt](https://github.com/kelektiv/node.bcrypt.js) for password hashing
- **Environment Management:** [dotenv](https://github.com/motdotla/dotenv)
- **Development Tooling:** [nodemon](https://nodemon.io/) for live reload
- **API Testing:** [Postman](https://www.postman.com/)

---

## ✨ Features

- 🏗 **Clean MVC Architecture:** Modular structure separating routes, controllers, models, and configuration.
- 🔐 **User Authentication:**
  - Secure registration with email duplication checks and password hashing via bcrypt pre-save hooks.
  - User login with password comparison.
  - User logout endpoint.
- 📝 **CRUD Operations for Posts:**
  - Create new posts with data validation.
  - Retrieve all posts.
  - Update posts by ID (`PATCH`).
  - Delete posts by ID (`DELETE`).
- ☁ **Cloud Database:** Seamless connection to MongoDB Atlas.

---

## 📁 Project Structure

```text
IntroToBackend/
├── backend/
│   └── src/
│       ├── config/
│       │   ├── constants.js          # App constants (e.g., DB name)
│       │   └── database.js           # MongoDB connection logic
│       ├── controllers/
│       │   ├── post.controller.js    # Post CRUD controllers
│       │   └── user.controller.js    # User auth controllers
│       ├── models/
│       │   ├── post.model.js         # Post schema & model
│       │   └── user.model.js         # User schema, password hashing & methods
│       ├── routes/
│       │   ├── post.route.js         # Post routes
│       │   └── user.route.js         # User routes
│       ├── app.js                    # Express app configuration & middleware
│       └── index.js                  # Entry point & server startup
├── .env.example                      # Template for environment variables
├── .gitignore                        # Files and secrets excluded from git
├── package.json                      # Project dependencies and scripts
└── README.md                         # Documentation
```

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- [MongoDB Atlas](https://www.mongodb.com/atlas) account (or a local MongoDB instance)
- [Postman](https://www.postman.com/) for API testing

### 1. Clone the repository

```bash
git clone https://github.com/ankitkumaryadav02042006-gif/IntroToBackend.git
cd IntroToBackend
```

### 2. Install dependencies

```bash
npm install
```

### 3. Setup environment variables

Create a `.env` file in the root directory (you can copy `.env.example`):

```bash
cp .env.example .env
```

Add your credentials inside `.env`:

```env
PORT=8000
MONGODB_URI="mongodb+srv://<username>:<password>@cluster.mongodb.net/intro-to-backend"
```

> **Note:** Never commit your `.env` file to version control. It is already included in `.gitignore`.

### 4. Start the server

For development with hot reload:
```bash
npm run dev
```

For production:
```bash
npm start
```

Upon successful startup, you will see:
```text
MongoDB connected !!!
Server is running at port : 8000
```

---

## 📡 API Endpoints

### 👥 User Routes (`/api/v1/users`)

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/api/v1/users/register` | Register a new user |
| `POST` | `/api/v1/users/login` | Log in an existing user |
| `POST` | `/api/v1/users/logout` | Log out a user |

#### Register User
* **URL:** `http://localhost:8000/api/v1/users/register`
* **Method:** `POST`
* **Headers:** `Content-Type: application/json`
* **Body:**
  ```json
  {
    "username": "ankit",
    "email": "ankit@example.com",
    "password": "strongPassword123"
  }
  ```

#### Login User
* **URL:** `http://localhost:8000/api/v1/users/login`
* **Method:** `POST`
* **Body:**
  ```json
  {
    "email": "ankit@example.com",
    "password": "strongPassword123"
  }
  ```

---

### 📝 Post Routes (`/api/v1/posts`)

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/api/v1/posts/create` | Create a new post |
| `GET` | `/api/v1/posts/getPosts` | Retrieve all posts |
| `PATCH` | `/api/v1/posts/update/:id` | Update a post by ID |
| `DELETE` | `/api/v1/posts/delete/:id` | Delete a post by ID |

#### Create Post
* **URL:** `http://localhost:8000/api/v1/posts/create`
* **Method:** `POST`
* **Body:**
  ```json
  {
    "name": "Ankit",
    "description": "Learning backend development with Express & MongoDB",
    "age": 20
  }
  ```

#### Get All Posts
* **URL:** `http://localhost:8000/api/v1/posts/getPosts`
* **Method:** `GET`

#### Update Post
* **URL:** `http://localhost:8000/api/v1/posts/update/<POST_ID>`
* **Method:** `PATCH`
* **Body:**
  ```json
  {
    "description": "Updated post description"
  }
  ```

#### Delete Post
* **URL:** `http://localhost:8000/api/v1/posts/delete/<POST_ID>`
* **Method:** `DELETE`

---

## 🧪 Testing with Postman

1. Ensure the backend server is running (`npm run dev`).
2. Open Postman and create a new request tab (`+`).
3. Set the HTTP method and URL as listed in the [API Endpoints](#-api-endpoints) table.
4. For `POST` and `PATCH` requests:
   - Select the **Body** tab &rarr; **raw** &rarr; select **JSON** format.
   - Enter your request payload and click **Send**.

---

## 👤 Author

* **Ankit Kumar Yadav** - [@ankitkumaryadav02042006-gif](https://github.com/ankitkumaryadav02042006-gif)
* Reference tutorial: [Intro to Backend Web Development](https://www.youtube.com/watch?v=KOutPbKc9UM) by Shivani.

---

## 📄 License

This project is licensed under the [ISC License](LICENSE).
