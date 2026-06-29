# WebSocket

## 1. Problem It Solves

Enables persistent bidirectional communication between client and server.

Eliminates repeated HTTP requests.

Supports low latency realtime communication.

---

## 2. When Should I Use It?

Use when:
* Client sends data continuously
* Server sends data continuously
* Bidirectional communication needed
* Low latency required

**Examples:**
* Chat systems
* Live driver tracking
* Multiplayer games
* Collaborative editing

---

## 3. When Should I Avoid It?

Avoid when:
* Realtime communication is unnecessary
* Simple request-response architecture is sufficient

**Examples:**
* Search APIs
* Product listing APIs

---

## 4. Alternative Options

Alternatives:
* Long Polling
* SSE
* gRPC Streaming

---

## 5. Tradeoffs

**Pros:**
* Persistent connection
* Low latency
* Bidirectional communication
* Battery efficient (compared to repeated polling)

**Cons:**
* Higher infrastructure complexity
* Connection management required (heartbeats, reconnects)
* More complex backend architecture (stateful servers)

---

## 6. Mobile System Design Use Cases

Used in:
* WhatsApp chat
* Uber driver tracking
* Multiplayer games
* Slack messaging

---

## 7. Interview Decision Framework

**Question:**
Design WhatsApp chat.

**Reasoning:**
* Messages are sent and received continuously.
* Realtime typing indicators are needed.
* Read receipts require instant server-to-client updates.
* Bidirectional realtime communication is a core requirement.

**Decision:**
Choose **WebSocket**.

---

## 8. Why NOT Other Options?

**Why NOT Short Polling?**
Too many unnecessary API calls and high battery drain.

**Why NOT SSE?**
SSE is one-way (server to client). In a chat system, the client also needs to send data (messages, typing status) continuously.

---

## 9. Real World Companies

Used by:
* WhatsApp
* Slack
* Discord
* Uber

---

## 10. Final Summary

Use when bidirectional realtime communication is required. Avoid for simple request-response systems.
