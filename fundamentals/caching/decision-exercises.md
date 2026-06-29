# Caching Decision Exercises

Practice designing caching strategies.

## Exercise 1: Frequently Accessed News Articles
**Scenario:** A news app where users frequently read the top 10 trending articles.
* **Requirements:** Reduce network load, handle large amounts of text and images.
* **Decision:** [ Disk Cache + Memory Cache / Memory Cache only ]
* **Reasoning:** 

## Exercise 2: Temporary Search Suggestions
**Scenario:** Showing search suggestions that change every few minutes.
* **Requirements:** Freshness is important, but we want to avoid hitting the network on every keystroke.
* **Decision:** [ Short TTL (e.g., 5 min) / Long TTL (e.g., 24 hours) ]
* **Reasoning:** 

## Exercise 3: User Authentication Token
**Scenario:** Storing the session token used for every API request.
* **Requirements:** Security, high availability throughout the app session.
* **Decision:** [ Encrypted SharedPrefs / Memory Cache ]
* **Reasoning:**
