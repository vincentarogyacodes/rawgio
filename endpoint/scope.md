# 1. Project Overview

This project produces reference documentation for RAWGIO's API. It tests and documents HTTP requests, JSON responses, and observed API behavior to help developers integrate with `GET /games` and `GET /games/{id}` endpoints.

# 2. Problem Statement/Objective

This API reference documentation is produced to thoroughly test and map RAWGIO's API requests and responses. The official API documentation for RAWGIO only includes a list of  `GET` parameters and sample JSON responses. It does not document API behavior that emerges through parameter testing. This project supplements RAWGIO's official API reference by documenting parameter inconsistencies that enable developers to confidently integrate with the API.

# 3. Objectives/Success Criteria

This documentation will only be deemed complete when it thoroughly tests and documents all endpoints listed in scope, while omitting those listed out of scope. It would also need to document all parameter behavior and inconsistencies, and provide a verifiable account of testing results.

# 4. In Scope

This project will only test and document the following RAWGIO endpoints:

- `GET /games`
- `GET /games/{id}`

# 5. Out of Scope

This project will not test or document the following RAWGIO endpoints:

- `GET /creator-roles`
- `GET /creators`
- `GET /creators/{id}`
- `GET /developers`
- `GET /developers/{id}`
- `GET /games/{game_pk}/additions`
- `GET /games/{game_pk}/development-team`
- `GET /games/{game_pk}/game-series`
- `GET /games/{game_pk}/parent-games`
- `GET /games/{game_pk}/screenshots`
- `GET /games/{game_pk}/stores`
- `GET /games/{id}/achievements`
- `GET /games/{id}/movies`
- `GET /games/{id}/reddit`
- `GET /games/{id}/suggested`
- `GET /games/{id}/twitch`
- `GET /games/{id}/youtube`
- `GET /genres`
- `GET /genres/{id}`
- `GET /platforms`
- `GET /platforms/lists/parents`
- `GET /platforms/{id}`
- `GET /publishers`
- `GET /publishers/{id}`
- `GET /stores`
- `GET /stores/{id}`
- `GET /tags`
- `GET /tags/{id}`

# 6. Audience

This API reference documentation is intended for developers working with RAWGIO's API, specifically with `GET /games` and `GET /games/{id}` endpoints. It is not intended for end users.

# 7. Testing Methodology

This API reference documentation was produced by using RAWG's free-tier API and following a rigorous testing methodology, involving the following practices:

 - Tested parameters against prescribed arguments and documented findings.
 - Tested parameters against false arguments to document API behavior and error responses.
 - Re-tested and verified findings that produced unexpected or ambiguous results before documenting them.

# 8. Assumptions & Constraints

## a. Assumptions

- RAWGIO's API is publicly available.
- HTTP requests return responses in JSON.

## b. Constraints

- Documentation reports testing as of July 19th, 2026. The API behavior is subject to change on RAWGIO's discretion.
- RAWGIO's source code is not publicly available.
- The API available to public has 20,000 call limit and restores after 30 days. 

# 9. Deliverables

- A project scope documentation with clearly outlined endpoint documentation for what's in scope and out of scope.
- A fully tested API reference documentation for RAWGIO's `GET /games` and `GET /games/{id}` endpoints that documents observed API behavior and JSON response inconsistencies.
- A README file summarizing the project, its purpose, and providing navigation to all documentation files.

# 10. Status & Milestones

|Done|In Progress|Pending|
|---|---|---|
|- Fully tested, documented, and ready to reference (search, ordering, and genres for `/games`).|- Scope document.|- Documentation for remaining parameters for `/games` and `/games/{id}`.|
