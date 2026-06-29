# Realtime Communication

Realtime communication determines how mobile applications receive updates from backend systems without requiring users to manually refresh data.

Choosing the correct realtime communication mechanism is an important system design decision because it directly affects:

* Latency
* Battery consumption
* Network usage
* Server load
* Infrastructure complexity
* User experience

The most common realtime communication mechanisms are:

## Short Polling

Client repeatedly asks server for updates at fixed intervals.

**Example:**
* Check inbox every 30 seconds

**Best suited for:**
* Infrequent updates
* Non-critical realtime systems

---

## Long Polling

Client sends request once.
Server keeps connection open until new data becomes available.

**Best suited for:**
* Legacy realtime systems
* Systems requiring occasional realtime updates

---

## WebSocket

Client establishes one persistent connection.
Both client and server can continuously exchange data.

**Best suited for:**
* Chat systems
* Live tracking
* Multiplayer games
* Collaboration systems

---

## Server Sent Events (SSE)

Persistent one-way connection.
Server continuously pushes updates to client.

**Best suited for:**
* Live score updates
* Stock market updates
* Notification streaming

---

## Comparison

| Feature | Short Polling | Long Polling | WebSocket | SSE |
| :--- | :--- | :--- | :--- | :--- |
| **Realtime** | Poor | Medium | Excellent | Excellent |
| **Bidirectional** | No | No | Yes | No |
| **Battery Usage** | High | Medium | Low | Low |
| **Complexity** | Low | Medium | Medium | Low |

---

## Interview Thinking Process

Do **NOT** think:
`Problem → Technology`

Always think:
1. **Problem**
2. **Realtime needed?**
3. **Who sends data?**
4. **Does client send continuously?**
5. **Does server send continuously?**
6. **Bidirectional communication needed?**
7. **Choose technology**
