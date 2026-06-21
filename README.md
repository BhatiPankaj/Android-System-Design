# Mobile System Design

The purpose of this repository is to prepare for Android/Mobile System Design interviews in a structured way. This repository focuses on solving common Mobile System Design interview questions using a standardized format.

## What is Mobile System Design?
Mobile System Design is the process of defining the architecture, components, modules, interfaces, and data for a mobile application to satisfy specified requirements. Unlike Backend System Design, which focuses on server scalability, throughput, and distributed systems, Mobile System Design focuses on:
- Resource constraints (Battery, CPU, Memory).
- Network variability (Offline-first, synchronization).
- User experience and UI performance.
- Local data persistence and caching.

## Interview Process
Typical Android interview process:
1. **DSA**: Data Structures and Algorithms.
2. **Android Fundamentals**: Lifecycle, Context, Threading, etc.
3. **Mobile System Design**: High-level and Low-level design.
4. **Managerial / Behavioral**: Cultural fit and leadership.

## Design Framework
Every system design question in this repo follows the same structure:
1. **Functional Requirements**
2. **Non Functional Requirements**
3. **High Level Architecture**
4. **API Design**
5. **Data Model**
6. **Local Storage**
7. **Data Flow**
8. **Offline Strategy**
9. **Error Handling**
10. **Performance Optimizations**
11. **Scalability**
12. **Trade-offs**
13. **Low Level Design**

## Reusable Concepts
Common concepts that are reused across different system designs.
- [Caching](./concepts/caching/)
- [Pagination](./concepts/pagination/)
- [Offline Sync](./concepts/offline-sync/)
- [WebSockets](./concepts/websocket/)
- [Notifications](./concepts/notifications/)
- [Retry Strategies](./concepts/retry-strategy/)
- [Conflict Resolution](./concepts/conflict-resolution/)
- [Modularization](./concepts/modularization/)

## Reusable Patterns
Standard patterns for common mobile features.
- [Search Pattern](./patterns/search-pattern.md)
- [Feed Pattern](./patterns/feed-pattern.md)
- [Chat Pattern](./patterns/chat-pattern.md)
- [Upload Pattern](./patterns/upload-pattern.md)
- [Download Pattern](./patterns/download-pattern.md)
- [Offline First Pattern](./patterns/offline-first-pattern.md)
- [Tracking Pattern](./patterns/tracking-pattern.md)
- [Notification Pattern](./patterns/notification-pattern.md)

## Navigation
Use the folders in this repository to explore specific design problems categorized by their core functionality.
- [Search](./search/)
- [Feed](./feed/)
- [Chat](./chat/)
- [Offline First](./offline-first/)
- [Upload](./upload/)
- [Download](./download/)
- [Notifications](./notifications/)
- [Realtime](./realtime/)
- [Architecture](./architecture/)

## Learning Order
Questions should be solved in the following order:

### Phase 1
1. YouTube Search
2. Offline Notes App
3. Instagram Feed
4. WhatsApp Chat

### Phase 2
5. Google Photos Upload
6. Netflix Download
7. Push Notification System
8. Uber Driver Tracking

### Phase 3
9. Large E-Commerce App
10. Analytics SDK
11. Feature Flag System
12. Deep Linking

## Contribution Workflow
For every new system design question:
1. Start with requirements.
2. Follow HLD template.
3. Follow LLD template.
4. Reuse concepts from [concepts/](./concepts/) folder.
5. Reuse patterns from [patterns/](./patterns/) folder.
6. Add diagrams.
7. Complete [interview checklist](./templates/interview-checklist.md).
8. Perform [interview evaluation](./templates/interview-evaluation.md).
