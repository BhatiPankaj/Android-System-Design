# Realtime Communication Decision Exercises

Use this framework for every question:

1. **Problem**
2. **Realtime needed?**
3. **Who sends data?**
4. **Does client send continuously?**
5. **Does server send continuously?**
6. **Bidirectional communication needed?**
7. **Choose technology**

---

## Question 1: Design WhatsApp Chat

### Needs:
* Send messages instantly
* Receive messages instantly
* Typing indicator
* Read receipts

### Options:
* Short Polling
* Long Polling
* WebSocket
* SSE

### Final Decision:
**WebSocket**

---

## Question 2: Design Uber Driver Tracking

### Needs:
* Driver sends location every second
* Server sends ETA updates
* Realtime communication required

### Options:
* Long Polling
* WebSocket
* SSE

### Final Decision:
**WebSocket**

---

## Question 3: Design Stock Market Live Price App

### Needs:
* Server continuously pushes price updates
* Client mostly receives data

### Options:
* Long Polling
* WebSocket
* SSE

### Final Decision:
**SSE**

---

## Question 4: Design Email Inbox Refresh

### Needs:
* Emails arrive occasionally
* Realtime updates not critical

### Options:
* Short Polling
* WebSocket
* SSE

### Final Decision:
**Short Polling**

---

## Learning Rule

Never think:
`Problem → Technology`

Always think:
1. **Problem**
2. **Requirements**
3. **Communication Direction**
4. **Frequency of Updates**
5. **Tradeoffs**
6. **Technology Decision**
