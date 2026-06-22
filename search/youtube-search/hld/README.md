# HLD: YouTube Search

## 1. Problem Statement
Design a mobile YouTube search experience. Users should be able to search for videos using keywords, receive real-time suggestions, view paginated results, and access their search history even when offline.

## 2. Functional Requirements

### Search & Suggestions
- **Query Entry:** Users can type queries in a search bar.
- **Dynamic Suggestions:** Show real-time search suggestions as the user types (debounce required).
- **Suggestion Interaction:** Users can execute a search by tapping a suggestion or submitting their typed query.
- **Trending Searches:** Display trending keywords when the search bar is focused but the query is empty.

### Search Results
- **Paginated Results:** Display search results in a scrollable list with pagination (lazy loading).
- **Pull-to-Refresh:** Allow users to manually refresh search results.
- **Empty States:** Gracefully handle "No Results Found" and empty history states.

### Search History
- **Persistence:** Maintain a history of recent searches in a local database.
- **Management:** Users can delete individual history entries or clear all history.
- **Offline Access:** Search history must be accessible without an internet connection.

### Analytics & Error Handling
- **Analytics:** Track queries, suggestion clicks, result clicks, and failed searches.
- **Retry Mechanism:** Provide a retry option if a search request fails due to network issues.

## 3. Non-Functional Requirements
- **Performance:** 
    - Suggestions should appear within **300ms**.
    - Search results should load within **1s** under normal network conditions.
- **Reliability:** Graceful degradation during network failures; transient errors should be retried.
- **Availability:** Use cached data to maintain usability during intermittent connectivity.
- **Offline Support:** Local history access and display of previously cached results (if valid).
- **Efficiency:** Minimize battery drain and data usage by optimizing network requests (caching, debouncing).
- **Scalability:** Architecture should support millions of daily active users.

## 4. Capacity Assumptions
- **Page Size:** 20 results per page.
- **Suggestion Limit:** 10 suggestions per query.
- **History Limit:** 20 most recent entries per user.
- **Trending Limit:** 20 trending keywords.
- **Cache TTL:** 15 minutes for search results.

## 5. Out of Scope
- User authentication and authorization.
- Video playback and streaming.
- Backend infrastructure (indexing, ranking algorithms, load balancing).

---

## 6. High Level Architecture
*(Diagram to be added in `diagrams/` folder)*

### Key Components:
- **Search UI:** Handles user input and displays suggestions/results.
- **Search ViewModel:** Manages UI state, handles debouncing for suggestions, and coordinates data fetching.
- **Search Repository:** Single source of truth; abstracts data sources (Remote vs. Local).
- **Remote Data Source:** Interfaces with YouTube Search APIs.
- **Local Data Source (Room/SQLDelight):** Stores search history and caches search results.
- **Suggestion Service:** Specifically handles the high-frequency suggestion API calls.

## 7. API Design (High Level)
- `GET /v1/suggestions?q={query}`: Returns list of strings.
- `GET /v1/search?q={query}&page={page_token}`: Returns paginated list of video objects.
- `GET /v1/trending`: Returns list of trending search terms.

## 8. Database Design (Local)
- **SearchHistory Table:** `id`, `query`, `timestamp`.
- **SearchResultCache Table:** `query`, `results_json`, `timestamp`, `page_token`.

## 9. Data Flow
1. User types -> ViewModel debounces -> Repository checks Cache -> Repository calls Remote Suggestion API -> UI updates.
2. User submits Search -> Repository checks Cache (TTL) -> Remote Search API -> Store in Local Cache -> UI updates.

## 10. Offline & Caching Strategy
- **History:** Always read from the Local Database.
- **Results:** If offline, show valid cached results from the last 15 minutes. Show a "No Internet" indicator for new searches.
- **Sync:** Sync history deletions with the backend when the connection is restored (if applicable).

## 11. Failure Handling
- **Network Failures:** Show "Retry" button and snackbar notifications.
- **Timeout:** Implement standard timeouts (e.g., 10s for search, 2s for suggestions).

## 12. Performance Optimizations
- **Debouncing:** 300ms delay on suggestion requests to save bandwidth/CPU.
- **Image Caching:** Use Coil/Glide for efficient thumbnail loading.
- **Prefetching:** Consider prefetching the next page when the user is near the bottom of the list.

## 13. Trade-offs
- **Client-side vs. Server-side History:** Storing history locally provides instant offline access but requires sync logic for multi-device consistency.
- **Cache TTL:** 15 minutes is a balance between fresh results and reducing server load.
