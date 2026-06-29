# Communication Protocols

Communication protocols define how a mobile application communicates with backend services.

Choosing the correct communication protocol is an important system design decision because it directly affects:

* Network performance
* Bandwidth usage
* Latency
* Caching strategies
* Realtime communication support
* Scalability
* Infrastructure complexity

The three most common communication protocols used in modern mobile applications are:

## REST

REST (Representational State Transfer) is the most widely used communication style where the client interacts with server resources using standard HTTP methods.

**Example:**
`GET /users/123`

**Best suited for:**
* Standard CRUD operations
* Request-response architecture
* Public APIs
* Most mobile applications

---

## GraphQL

GraphQL allows the client to request only the specific data fields it needs instead of the server deciding the response structure.

**Example:**
```graphql
query {
  user(id: 123) {
    name
    profilePicture
  }
}
```

**Best suited for:**
* Complex screens requiring multiple resources
* Mobile bandwidth optimization
* Applications where over-fetching is a concern

---

## gRPC

gRPC is a high-performance communication protocol developed by Google.

It uses:
* HTTP/2
* Protocol Buffers (binary serialization)

instead of JSON.

**Example:**
`rpc GetUser(UserRequest) returns (UserResponse);`

**Best suited for:**
* Internal service communication
* High throughput systems
* Realtime streaming systems
* Performance critical applications

---

## Comparison

| Feature | REST | GraphQL | gRPC |
| :--- | :--- | :--- | :--- |
| **Learning Curve** | Easy | Medium | Hard |
| **Uses JSON** | Yes | Yes | No |
| **Uses Binary** | No | No | Yes |
| **Performance** | Medium | Good | Excellent |
| **Streaming Support** | No | Limited | Excellent |
| **Caching** | Easy | Hard | Medium |
| **Mobile Bandwidth Efficiency** | Medium | Good | Excellent |
| **Debugging** | Easy | Medium | Hard |

---

## Interview Thinking Process

Do **NOT** think:
`Problem → Technology`

Instead think:
1. **Problem**
2. **Requirements**
3. **Constraints**
4. **Possible Options**
5. **Trade-offs**
6. **Technology Choice**

This is the expected approach in system design interviews.
