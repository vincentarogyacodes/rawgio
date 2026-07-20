yaml
---
---

# RAWG.IO API Reference Documentation

This is a community reference of the RAWG.IO public REST API through independent testing and verification. The project supplements the official RAWG.IO API reference by documenting verified parameter behavior, observed implementation details, and API inconsistencies for the `GET /games` and `GET /games/{id}` endpoints.

# Live Documentation

[View the live documentation](https://vincentarogyacodes.github.io/rawgio/)

# Project Overview

This project was created to address gaps in RAWG.IO's official API reference. While the official documentation describes available endpoints and query parameters, it provides limited information about observed parameter behavior and implementation details identified through testing. This project supplements the official reference by independently testing and documenting the `GET /games` and `GET /games/{id}` endpoints, including verified parameter behavior, observed inconsistencies, and implementation details to help developers integrate with the API more confidently.

# Objectives

The objective of this project is to produce a comprehensive API reference for RAWG.IO's public API by independently testing and documenting `GET /games` and `GET /games/{id}` endpoints, including verified parameter behavior, implementation details, and observed inconsistencies. 

# Documentation Scope

### In Scope

- `GET /games`
- `GET /games/{id}`

### Out of Scope

- All other RAWG.IO endpoints.

For a detailed breakdown of project scope, assumptions, and constraints, see the [Project Scope](https://github.com/vincentarogyacodes/rawgio/blob/main/endpoint/scope.md) document.

# Documentation Methodology

Documentation is produced using the following workflow:

- Review RAWG.IO's official API reference.
- Develop hypotheses about endpoint behavior.
- Validate endpoint behavior using Postman.
- Compare observed behavior with the official documentation.
- Document reproducible findings and observed implementation details.
- Manage documentation revisions using Git and GitHub.

# Repository Structure

```text
rawgio/
├── README.md
├── index.md
└── endpoints/
    ├── games-list.md
    └── scope.md
```
# Technologies Used

|Technology|Purpose|
|---|---|
|REST API|API under documentation|
|HTTP|Testing requests and responses|
|Postman|API testing|
|Git|Version Control|
|GitHub|Repository hosting|
|GitHub Pages|Documentation publishing|
|Markdown|Documentation authoring|
|JSON|Response analysis|

# Documentation Features

This API reference includes the following features:

- Parameter reference table
- HTTP request examples
- JSON response analysis
- Parameter notes
- Observed implementation details and inconsistencies
- Edge cases
- Cross references

# Project Status

🚧 Active Development

Documentation is currently under active development. Additional endpoints and parameter details will be added as testing progresses.

# Contributing

This project is currently maintained by the author.

# Disclaimer

All documented observations are based on independent testing of the publicly accessible API.

# License

This project is licensed under the MIT License.
