# Communication Protocol Decision Exercises

This file contains interview-style questions to practice choosing the correct communication protocol.

The goal is **NOT** memorizing answers.
The goal is **learning engineering decision making**.

### Approach:
1. **Problem**
2. **Requirements**
3. **Constraints**
4. **Possible Options**
5. **Trade-offs**
6. **Final Decision**

---

## Question 1

### Problem
Design YouTube Search system.

Users can:
* Search videos
* Receive paginated search results
* Receive search suggestions

**Which communication protocol should be used?**

**Options:**
* REST
* GraphQL
* gRPC

---

### Thinking Process

**Requirements:**
* Request-response communication
* No realtime communication needed
* Search response structure is predictable

**Constraints:**
* Low infrastructure complexity preferred
* Standard mobile backend architecture

**Possible options:**

**REST**
* Simple
* Easy caching
* Widely supported

**GraphQL**
* Can reduce over-fetching
* Added backend complexity

**gRPC**
* High performance
* Streaming unnecessary

---

### Final Decision
Choose **REST**.

**Reason:**
Search is request-response based. No continuous communication required. REST provides the best balance of simplicity and functionality.

---

## Question 2

### Problem
Design WhatsApp typing indicator.

While user types:
* Typing status should be updated continuously
* Receiver should see typing status instantly

**Choose communication protocol.**

**Options:**
* REST
* WebSocket
* gRPC

---

### Thinking Process

**Requirements:**
* Realtime communication
* Continuous updates
* Low latency
* Persistent connection required

**REST**
* Repeated HTTP requests
* High overhead

**WebSocket**
* Persistent connection
* Bidirectional communication
* Low latency

**gRPC**
* Supports streaming
* High performance
* More infrastructure complexity

---

### Final Decision
Choose **WebSocket**.

**Reason:**
Typing indicator requires persistent bidirectional realtime communication. WebSocket is widely used for chat systems. gRPC is possible but adds unnecessary complexity for this specific feature.

---

## Question 3

### Problem
Design Instagram Feed.

Users:
* Load 20 posts
* Scroll infinitely
* Load next posts

**Choose communication protocol.**

**Options:**
* REST
* GraphQL
* gRPC

---

### Thinking Process

**Requirements:**
* Pagination required
* Response size optimization important
* Request-response communication

**REST**
* Easy caching
* Possible over-fetching

**GraphQL**
* Client requests only required fields
* Better bandwidth optimization

**gRPC**
* Streaming unnecessary
* Infrastructure complexity high

**Additional consideration:**
Offset pagination becomes inefficient for very large datasets. **Cursor pagination preferred.**

---

### Final Decision

**Option 1:** REST + Cursor Pagination
**Option 2:** GraphQL + Cursor Pagination

*Depends on bandwidth optimization requirements.*

---

## Learning Rule

Never think:
`Problem → Technology`

Always think:
**Problem**
↓
**Requirements**
↓
**Constraints**
↓
**Compare Options**
↓
**Trade-offs**
↓
**Technology Decision**
