# GraphQL

## What is GraphQL?

GraphQL allows clients to request only specific fields they need.

Unlike REST, the server does **NOT** decide the response structure. The client decides.

---

## Example

Instead of a REST call like `GET /user/123`, you use a query:

```graphql
query {
  user(id: 123) {
    name
    profilePicture
  }
}
```

The server returns only the requested fields.

---

## Why GraphQL Exists

GraphQL solves the **REST over-fetching** problem.

**Problem with REST:**
* App needs 2 fields.
* Server returns 10 fields.
* *Extra bandwidth wasted.*

---

## Advantages

* **Avoids over-fetching:** Get exactly what you need.
* **Client controls response structure:** Flexibility for the frontend.
* **Multiple resources in one request:** Fetch related data (e.g., user + posts) in a single round trip.
* **Better mobile bandwidth usage:** Crucial for users on slow or metered networks.

---

## Disadvantages

* **Backend implementation complexity:** Requires a more complex server setup (resolvers, schema).
* **Harder caching compared to REST:** Since queries are dynamic, standard HTTP caching (by URL) is less effective.
* **Query parsing overhead:** The server must parse and validate every query.
* **Maintainability:** Large, complex schemas can become difficult to manage.

---

## Mobile Use Cases

GraphQL is suitable for:
* **Instagram Feed:** Fetching only visible fields for a post.
* **Dashboard screens:** Aggregating data from multiple services.
* **Complex profile screens:** Fetching user details, followers, and activity in one go.
* **Super apps:** Where multiple mini-apps share a unified data layer.

---

## When NOT to Use GraphQL

Avoid when:
* You have simple CRUD APIs.
* Backend complexity is unnecessary for the project's scale.
* Standard REST APIs already exist and fulfill the requirements efficiently.

---

## Interview Decision Example

**Question:**
Design Instagram Feed

**Reasoning:**
* The feed may require only selected fields (e.g., thumbnail, username, like count) for each post.
* REST can over-fetch unnecessary details (e.g., full comment list, metadata).
* GraphQL allows the mobile client to request only required fields, optimizing bandwidth.

**Trade-off:**
* Caching becomes more complex (requires client-side normalization or persistent queries).

**Possible Choice:**
**GraphQL**.
