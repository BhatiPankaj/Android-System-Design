# Long Polling

## 1. Problem It Solves

Reduces unnecessary repeated requests by keeping the connection open until new data becomes available.

Improves efficiency compared to short polling.

---

## 2. When Should I Use It?

Use when:
* Realtime updates are needed occasionally.
* WebSocket infrastructure is unavailable.
* A simpler realtime system is required compared to full duplex connections.

**Examples:**
* Basic chat systems
* Notification systems

---

## 3. When Should I Avoid It?

Avoid when:
* Continuous bidirectional communication is required.
* Very frequent updates are required.

**Examples:**
* Live tracking (e.g., Uber)
* Multiplayer games

---

## 4. Alternative Options

Alternatives:
* Short Polling
* WebSocket
* SSE

---

## 5. Tradeoffs

**Pros:**
* Fewer unnecessary requests than short polling.
* Better realtime experience (lower perceived latency).

**Cons:**
* Connection repeatedly opens and closes.
* More complex to implement on the backend than short polling.
* Still less efficient than WebSocket for high-frequency data.

---

## 6. Mobile System Design Use Cases

Used in:
* Legacy chat systems
* Legacy notification systems

---

## 7. Interview Decision Framework

**Question:**
Design a simple notification system.

**Reasoning:**
* Need occasional realtime updates.
* Short polling wastes too many requests when no updates are present.
* A persistent WebSocket connection might be overkill and harder to scale for this specific use case.

**Decision:**
Choose **Long Polling**.

---

## 8. Why NOT Other Options?

**Why NOT Short Polling?**
Too many unnecessary requests leading to high battery and server load.

**Why NOT WebSocket?**
Maintaining a persistent connection may be unnecessary and resource-intensive for infrequent updates.

---

## 9. Real World Companies

Historically used in:
* Older chat systems
* Legacy web applications

---

## 10. Final Summary

Use when occasional realtime updates are needed. Avoid for continuous communication systems.
