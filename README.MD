# Todo List API

This is a simple Todo List API written in Rust using the Actix web framework. The API allows you to manage todo list entries with the following operations: get, post, put, and remove.

## Base URL

```
http://127.0.0.1:8080/todolist/entries
```

## Endpoints

### Get All Entries

**Endpoint:** `GET /todolist/entries`

**Description:** Retrieves all todo list entries.

**Request:**

```http
GET /todolist/entries HTTP/1.1
Host: 127.0.0.1:8080
```

**Response:**

- **Status:** 200 OK
- **Body:**

```json
[
  {
    "id": "a unique UUID",
    "title": "Sample Entry",
    "completed": false
  }
]
```

### Add a New Entry

**Endpoint:** `POST /todolist/entries`

**Description:** Adds a new todo list entry.

**Request:**

```http
POST /todolist/entries HTTP/1.1
Host: 127.0.0.1:8080
Content-Type: application/json

{
  "id": "a unique UUID",
  "title": "New Entry",
  "completed": false
}
```

**Response:**

- **Status:** 201 Created

### Update an Entry

**Endpoint:** `PUT /todolist/entries/{id}`

**Description:** Updates an existing todo list entry.

**Request:**

```http
PUT /todolist/entries/{id} HTTP/1.1
Host: 127.0.0.1:8080
Content-Type: application/json

{
  "id": "a unique UUID",
  "title": "Updated Entry",
  "completed": true
}
```

**Response:**

- **Status:** 200 OK (if the entry was updated)
- **Status:** 404 Not Found (if the entry does not exist)

### Remove an Entry

**Endpoint:** `DELETE /todolist/entries/{id}`

**Description:** Removes a todo list entry.

**Request:**

```http
DELETE /todolist/entries/{id} HTTP/1.1
Host: 127.0.0.1:8080
```

**Response:**

- **Status:** 204 No Content (if the entry was removed)
- **Status:** 404 Not Found (if the entry does not exist)

## Running the Server

To run the server, use the following commands:

1. Clone the repository:

```sh
git clone https://github.com/yourusername/todolist-api.git
cd todolist-api
```

2. Set up your environment:

Make sure you have Rust installed. If not, you can install it from [rust-lang.org](https://www.rust-lang.org/).

3. Run the server:

```sh
cargo run
```

The server will start on `http://127.0.0.1:8080`.