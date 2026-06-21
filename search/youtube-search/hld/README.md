### Problem Statement: 
Design a mobile Youtube search. User can search videos using their keywords. 
On typing we need to show search suggestions. User can search using his query or can click on suggested suggestion.
Need to show paginated Search result. User can access search history. User can access search history in offline mode also.
And also need to show trending searches. 

### Assumptions:
    1. backend systems is handling Search indexing.
    2. Ranking algorithm are owned by backend systems.
    3. Authentication is already implemented.
    4. We'll use existings search APis
    5. We don't need to support video playback.

### Function Requirements:

#### Search
    - User can search videos by typing their query.
    - User can click on suggestion or use their query to execute search.

#### Suggestions
    - we need to show suggestions when user is typing his query.
    - Need to update suggestions dynamically.

#### History
    - Need to maintain recent search in database.
    - User can delete any specific search history.
    - Need to allow to clear all history.

#### Trending
    - Need to show trending searches when user clicks on serach bar and query is empty.

#### Result
    - Show paginated search result to the user
    - Use can pull to refresh the result

#### Error Handling
    - If there is any failure of search request then user can retry to request the same search]


### Non-Function Requirements: 

#### Performance
    - Suggestions should be shown under 300ms
    - User should see the search result under 1s

#### Scalability
    - Support millions of users

#### Reliability
    - Search Failures should be handled properly

#### Offline
    - User can check search in offline mode also.

#### Battery
    - Minimize unnecessary network requests

### Capacity Assumptions
    - Page size for pagination is 20
    - Suggestion limit is 10
    - History size limit is 20
    - Cache TTL: 15min
    - Trending limit: 20


























