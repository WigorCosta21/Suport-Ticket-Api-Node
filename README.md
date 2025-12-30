# 🎫 Support Tickets API

A simple **REST API** for managing **support tickets**, built with **Node.js** using **modern JavaScript (ES Modules)** and JSON file persistence.

---

## 📌 Features

- ✅ Create support tickets
- 📋 List tickets
- 🔍 Filter tickets by **status**
- ✏️ Update ticket data
- 🔒 Close tickets with a solution
- 🗑️ Delete tickets
- 💾 JSON file persistence

---

## 🛠️ Technologies Used

- Node.js
- JavaScript (ES Modules)
- Native HTTP API (no frameworks)
- JSON as a local database

---

## 📁 Project Structure

```bash
src/
├── controllers/
│   └── tickets/
│       ├── create.js
│       ├── index.js
│       ├── update.js
│       ├── update-status.js
│       └── remove.js
├── database/
│   ├── database.js
│   └── db.json
├── middlewares/
│   ├── jsonHandler.js
│   └── routeHandler.js
├── routes/
│   ├── index.js
│   └── tickets.js
├── utils/
│   ├── extractQueryParams.js
│   └── parseRoutePath.js
└── server.js
```

---

## 🚀 Getting Started

### 1️⃣ Requirements

- Node.js **v18+**

### 2️⃣ Install dependencies

```bash
npm install
```

### 3️⃣ Run the server (development mode)

```bash
npm run dev
```

The server will start at:

```
http://localhost:3333
```

---

## 📌 API Endpoints

### 🔹 Create Ticket

**POST** `/tickets`

```json
{
  "user_name": "John Doe",
  "title": "System error",
  "description": "I can't access my account"
}
```

---

### 🔹 List Tickets

**GET** `/tickets`

---

### 🔹 Filter Tickets by Status

**GET** `/tickets?status=open`

Status examples:

- `open`
- `closed`

---

### 🔹 Update Ticket

**PUT** `/tickets/:id`

```json
{
  "user_name": "John Doe",
  "title": "Updated title",
  "description": "Updated description"
}
```

---

### 🔹 Close Ticket (Add Solution)

**PATCH** `/tickets/:id/close`

```json
{
  "solution": "User password was reset successfully"
}
```

➡️ This route automatically sets the ticket status to `closed`.

---

### 🔹 Delete Ticket

**DELETE** `/tickets/:id`

---

## 🧠 Business Rules

- Each ticket has a **unique ID**
- Each ticket is associated with a **user_name**
- Default status when creating a ticket is `open`
- Closing a ticket sets the status to `closed` and stores a `solution`
- Data is persisted in the `db.json` file
- Filters are applied using **Query Parameters**

---

## 📄 Ticket Example

```json
{
  "id": "a1b2c3",
  "user_name": "John Doe",
  "title": "Login issue",
  "description": "Invalid password",
  "status": "closed",
  "solution": "User password was reset successfully",
  "created_at": "2025-12-27T12:00:00.000Z",
  "updated_at": "2025-12-28T12:00:00.000Z"
}
```

---

## 📚 Concepts Applied

- Separation of concerns (controllers, routes, middlewares)
- Route handling using Regex
- Query parameters
- CRUD operations
- Clean API architecture

---

## 👨‍💻 Author

**Wigor Ribeiro da Costa**

---

## 📄 License

This project is licensed under the **ISC License**.

---
