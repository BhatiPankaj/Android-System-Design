# REST

## What is REST?

REST (Representational State Transfer) is a communication style where clients interact with server resources using HTTP.

**Example:**
`GET /videos/123`

The server returns data in JSON format.

**Example response:**
```json
{
  "title": "Android Tutorial",
  "views": 100000
}
```

---

## How REST Works

Client sends HTTP request.

1. **Mobile App** sends **HTTP Request**.
2. **Server** processes request.
3. **Server** sends **JSON Response**.
4. **App** parses JSON.

---

## Common HTTP Methods

* **GET** → Fetch data
* **POST** → Create data
* **PUT** → Replace entire resource
* **PATCH** → Partial update
* **DELETE** → Remove resource

---

## Advantages

* Easy to understand
* Widely adopted
* Easy caching support
* Standardized HTTP methods
* Easy debugging

---

## Disadvantages

### Over-fetching
Server may return unnecessary fields.

**Example:**
App needs:
* username
* profilePicture

Server returns:
* username
* profilePicture
* email
* phone
* address

*Extra bandwidth wasted.*

### Multiple API Calls
Sometimes multiple endpoints are required for a single screen.

**Example:**
1. `GET /profile`
2. `GET /feed`
3. `GET /notifications`

*This increases latency and battery consumption.*

---

## Mobile Use Cases

REST is suitable for:
* YouTube Search
* E-commerce product listing
* User profile APIs
* Notes applications
* Feed loading systems

---

## When NOT to Use REST

Avoid when:
* Realtime communication is required.
* Continuous streaming is required.
* Bidirectional communication is required.

**Examples:**
* WhatsApp Chat
* Uber Live Tracking

---

## Interview Decision Example

**Question:**
Design YouTube Search

**Reasoning:**
* Search is request-response based.
* No persistent connection is required.
* REST is simple, widely supported, and sufficient for this use case.

**Therefore:**
Choose **REST**.
