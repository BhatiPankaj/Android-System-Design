# Pagination Decision Exercises

Practice choosing the right pagination strategy.

## Exercise 1: Twitter-like Feed
**Scenario:** A social media feed where new posts are added frequently at the top.
* **Requirements:** Avoid duplicate items when the user scrolls down after new items were added.
* **Decision:** [ Cursor Pagination / Offset Pagination ]
* **Reasoning:** 

## Exercise 2: Admin Dashboard User List
**Scenario:** An internal tool to manage 500 users where admins often need to jump to a specific page or sort by different columns.
* **Requirements:** Page jumping support, simple implementation for static data.
* **Decision:** [ Offset Pagination / Keyset Pagination ]
* **Reasoning:** 

## Exercise 3: Massive Log Viewer
**Scenario:** A system to view billions of log entries sorted by timestamp.
* **Requirements:** Performance at scale, no performance degradation for deep pages.
* **Decision:** [ Keyset Pagination / Offset Pagination ]
* **Reasoning:**
