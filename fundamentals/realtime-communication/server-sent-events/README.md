# Server Sent Events (SSE)

## 1. Problem It Solves

Allows server to continuously push updates to client over one persistent connection.

Suitable when client mostly receives updates.

---

## 2. When Should I Use It?

Use when:
* Server continuously sends updates
* Client mostly listens
* Bidirectional communication is unnecessary

**Examples:**
* Stock market updates
* Live sports score
* Live notifications

---

## 3. When Should I Avoid It?

Avoid when:
* Client also sends data continuously
* Bidirectional communication is required

**Examples:**
* Chat systems
* Driver tracking

---

## 4. Alternative Options

Alternatives:
* Long Polling
* WebSocket

---

## 5. Tradeoffs

**Pros:**
* Low latency
* Persistent connection
* Lower complexity than WebSocket
* Efficient for one-way updates

**Cons:**
* No bidirectional communication
* Less flexible than WebSocket

---

## 6. Mobile System Design Use Cases

Used in:
* Stock market apps
* Live score applications
* Event streaming systems

---

## 7. Interview Decision Framework

**Question:**
Design stock market app.

**Reasoning:**
* Server continuously pushes price updates.
* Client mostly receives updates.
* Bidirectional communication is unnecessary.

**Decision:**
Choose **SSE**.

---

## 8. Why NOT Other Options?

**Why NOT WebSocket?**
Bidirectional communication is unnecessary for a simple one-way price update stream.

**Why NOT Short Polling?**
Too many unnecessary repeated requests leading to high battery drain and latency.

---

## 9. Real World Companies

Used in:
* Live dashboard systems
* Financial applications
* Sports applications

---

## 10. Final Summary

Use when server continuously pushes data. Avoid when bidirectional communication is required.
