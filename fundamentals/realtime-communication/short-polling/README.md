# Short Polling

## 1. Problem It Solves

Allows client to periodically check server for updates.

Useful when data changes occasionally and strict realtime communication is not required.

---

## 2. When Should I Use It?

Use when:
* Updates are infrequent
* Realtime communication is not critical
* Simplicity is preferred

**Examples:**
* Email inbox refresh
* Weather updates
* Order history refresh

---

## 3. When Should I Avoid It?

Avoid when:
* Frequent updates required
* Low latency is important
* Battery efficiency matters

**Examples:**
* Chat systems
* Live tracking
* Live score updates

---

## 4. Alternative Options

Alternatives:
* Long Polling
* WebSocket
* SSE

---

## 5. Tradeoffs

**Pros:**
* Very simple implementation
* Easy backend support
* Easy debugging

**Cons:**
* Many unnecessary API calls
* Battery drain
* High server load
* Poor realtime experience

---

## 6. Mobile System Design Use Cases

Used in:
* Email refresh systems
* Weather apps
* Basic dashboard refresh

---

## 7. Interview Decision Framework

**Question:**
Design email refresh system.

**Reasoning:**
* Emails arrive occasionally.
* Realtime updates are not critical.
* Simple implementation is sufficient.

**Decision:**
Choose **Short Polling**.

---

## 8. Why NOT Other Options?

**Why NOT WebSocket?**
Persistent connection is unnecessary for occasional updates.

**Why NOT SSE?**
Continuous server updates are unnecessary.

---

## 9. Real World Companies

Historically used in:
* Older email clients
* Basic dashboard systems

---

## 10. Final Summary

Use when updates are infrequent. Avoid for realtime systems.
