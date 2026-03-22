# GitHub Access Report Service

## Overview

This project is a Spring Boot application that connects to GitHub and generates a report showing which users have access to which repositories inside a GitHub organization.

The service authenticates using GitHub Personal Access Token, retrieves repositories, fetches collaborators, aggregates the data, and exposes a REST API endpoint that returns the access report in JSON format.

---

## How to run the project

1. Clone the repository

git clone https://github.com/DevLord01/github-access-report-service

2. Open project in IDE (IntelliJ / VS Code)

3. Set GitHub token as environment variable

GITHUB_TOKEN=your_token_here

4. Run Spring Boot application

Run GithubReportApplication.java

5. API will run on

http://localhost:8080

---

## Authentication configuration

Authentication is done using GitHub Personal Access Token.

Steps:

1. Go to GitHub Settings
2. Developer Settings
3. Personal Access Tokens
4. Generate token with repo access
5. Set token as environment variable

GITHUB_TOKEN=xxxx

The token is sent in Authorization header when calling GitHub API.

---

## API Endpoint

GET /api/access-report/{organization}

Example:

http://localhost:8080/api/access-report/test-org

Response example:

{
  "user1": ["repo1", "repo2"],
  "user2": ["repo3"]
}

This API returns which users have access to which repositories.

---

## Assumptions / Design Decisions

- Used Spring Boot for REST API
- Used GitHub REST API for data
- Used HashMap to aggregate users and repos
- Designed to support 100+ repos and 1000+ users
- Avoided unnecessary API calls
- Used service layer for clean architecture
- Token must have permission to read repositories

---

## Author

Aniket Gaikwad
