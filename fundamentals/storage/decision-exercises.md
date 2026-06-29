# Storage Decision Exercises

Practice choosing the right local storage mechanism.

## Exercise 1: User Preferences
**Scenario:** Storing simple settings like `isDarkModeEnabled` or `preferredLanguage`.
* **Requirements:** Small data size, simple API, fast access.
* **Decision:** [ Key-Value (DataStore/SharedPreferences) / SQLite ]
* **Reasoning:** 

## Exercise 2: Offline-First Notes App
**Scenario:** An app where users write long-form notes with titles, tags, and timestamps, requiring complex searching and filtering.
* **Requirements:** Relational data, complex queries, data integrity.
* **Decision:** [ SQLite (Room) / File Storage ]
* **Reasoning:** 

## Exercise 3: Profile Picture Storage
**Scenario:** Saving the user's high-resolution profile picture for offline display.
* **Requirements:** Handling binary large objects, efficient disk usage.
* **Decision:** [ File Storage / SQLite ]
* **Reasoning:**
