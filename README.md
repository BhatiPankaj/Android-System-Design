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

# Phase 0 — Fundamentals
Before solving system design interview questions, study the following fundamentals.

## Communication Protocols
- [REST](./fundamentals/communication/rest/)
- [GraphQL](./fundamentals/communication/graphql/)
- [gRPC](./fundamentals/communication/grpc/)

## Realtime Communication
- [Short Polling](./fundamentals/realtime-communication/short-polling/)
- [Long Polling](./fundamentals/realtime-communication/long-polling/)
- [WebSocket](./fundamentals/realtime-communication/websocket/)
- [SSE](./fundamentals/realtime-communication/server-sent-events/)

## Pagination
- [Offset Pagination](./fundamentals/pagination/offset-pagination/)
- [Cursor Pagination](./fundamentals/pagination/cursor-pagination/)
- [Keyset Pagination](./fundamentals/pagination/keyset-pagination/)
- [Page Number Pagination](./fundamentals/pagination/page-number-pagination/)

## Storage
- [SQLite](./fundamentals/storage/sqlite-room/)
- [Key Value Storage](./fundamentals/storage/key-value-storage/)
- [File Storage](./fundamentals/storage/file-storage/)
- [Object Storage](./fundamentals/storage/object-storage/)
- [CDN](./fundamentals/storage/cdn/)

## Caching
- [Memory Cache](./fundamentals/caching/memory-cache/)
- [Disk Cache](./fundamentals/caching/disk-cache/)
- [TTL](./fundamentals/caching/ttl/)
- [Cache Invalidation](./fundamentals/caching/cache-invalidation/)
- [LRU Cache](./fundamentals/caching/lru-cache/)

## Network Resilience
- [Retry](./fundamentals/network-resilience/retry/)
- [Exponential Backoff](./fundamentals/network-resilience/exponential-backoff/)
- [Circuit Breaker](./fundamentals/network-resilience/circuit-breaker/)
- [Timeout](./fundamentals/network-resilience/timeout/)
- [Rate Limiting](./fundamentals/network-resilience/rate-limiting/)
- [Idempotency](./fundamentals/network-resilience/idempotency/)

## Synchronization
- [Pull Sync](./fundamentals/synchronization/pull-sync/)
- [Push Sync](./fundamentals/synchronization/push-sync/)
- [Conflict Resolution](./fundamentals/synchronization/conflict-resolution/)
- [Source of Truth](./fundamentals/synchronization/source-of-truth/)
- [Eventual Consistency](./fundamentals/synchronization/eventual-consistency/)

## Security
- [HTTPS](./fundamentals/security/https/)
- [TLS](./fundamentals/security/tls/)
- [OAuth](./fundamentals/security/oauth/)
- [JWT](./fundamentals/security/jwt/)
- [API Keys](./fundamentals/security/api-keys/)
- [Certificate Pinning](./fundamentals/security/certificate-pinning/)

## Media Systems
- [Chunk Upload](./fundamentals/media-systems/chunk-upload/)
- [Multipart Upload](./fundamentals/media-systems/multipart-upload/)
- [Compression](./fundamentals/media-systems/compression/)
- [Resume Download](./fundamentals/media-systems/resume-download/)

## Architecture Patterns
- [MVVM](./fundamentals/architecture-patterns/mvvm/)
- [Repository Pattern](./fundamentals/architecture-patterns/repository-pattern/)
- [Single Source of Truth](./fundamentals/architecture-patterns/single-source-of-truth/)
- [Offline First](./fundamentals/architecture-patterns/offline-first/)
- [Event Driven Architecture](./fundamentals/architecture-patterns/event-driven-architecture/)

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
- [Search Pattern](interview-patterns/search-pattern.md)
- [Feed Pattern](interview-patterns/feed-pattern.md)
- [Chat Pattern](interview-patterns/chat-pattern.md)
- [Upload Pattern](interview-patterns/upload-pattern.md)
- [Download Pattern](interview-patterns/download-pattern.md)
- [Offline First Pattern](interview-patterns/offline-first-pattern.md)
- [Tracking Pattern](interview-patterns/tracking-pattern.md)
- [Notification Pattern](interview-patterns/notification-pattern.md)

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
5. Reuse patterns from [patterns/](interview-patterns/) folder.
6. Add diagrams.
7. Complete [interview checklist](./templates/interview-checklist.md).
8. Perform [interview evaluation](./templates/interview-evaluation.md).
