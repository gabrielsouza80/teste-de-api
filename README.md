# API Testing Portfolio – JSONPlaceholder

## 1. Project Overview

This repository presents a professional API testing portfolio built around the public JSONPlaceholder REST API. It demonstrates how to design, document, execute, and automate API tests with Postman, Newman, JavaScript assertions, and GitHub Actions.

JSONPlaceholder is a fake service, so POST, PUT, PATCH, and DELETE requests simulate typical REST behavior without persisting real changes. That limitation is documented in this project to show practical QA judgment, not just test execution.

## 2. Purpose of the Project

The goal of this portfolio is to show a clear QA approach for REST API testing. The project focuses on manual API validation, reusable Postman collections, basic contract checks, negative scenarios, and automated execution in CI/CD.

## 3. Technologies Used

- Postman
- Newman
- JavaScript assertions inside Postman tests
- JSONPlaceholder REST API
- GitHub Actions
- Markdown documentation

## 4. API Under Test

Base URL: https://jsonplaceholder.typicode.com/

Covered resources and endpoints:

- GET /posts
- GET /posts/{id}
- GET /posts/{id}/comments
- GET /comments?postId={id}
- POST /posts
- PUT /posts/{id}
- PATCH /posts/{id}
- DELETE /posts/{id}
- GET /users
- GET /users/{id}
- GET /users/{id}/todos
- GET /todos?completed=true

## 5. Test Coverage

The Postman collection includes:

- Status code validation
- Response time validation
- Response body validation
- Required fields validation
- Data type validation
- Array validation
- Query parameter validation
- Negative and edge case examples
- Basic contract validation for key resources

Examples of assertions covered in the collection:

- Status code is 200, 201, or the expected code
- Response time is below 1000ms
- Response body is JSON
- Required fields exist
- id is a number
- title, body, email, and name exist where applicable
- List endpoints return arrays
- Filtered endpoints return only expected data

## 6. Project Structure

```text
.
├── postman/
│   ├── jsonplaceholder-api-tests.postman_collection.json
│   └── jsonplaceholder-environment.postman_environment.json
├── docs/
│   ├── api-test-strategy.md
│   ├── bug-report-examples.md
│   ├── execution-guide.md
│   └── test-scenarios.md
├── .github/
│   └── workflows/
│       └── api-tests.yml
├── package.json
└── .gitignore
```

## 7. How to Run with Postman

1. Open Postman.
2. Import the collection from postman/jsonplaceholder-api-tests.postman_collection.json.
3. Import the environment from postman/jsonplaceholder-environment.postman_environment.json.
4. Select the JSONPlaceholder Environment.
5. Run the collection or individual folders from the Collection Runner.

## 8. How to Run with Newman

Install dependencies first:

```bash
npm install
```

Run the API tests:

```bash
npm test
```

Run the Newman collection directly:

```bash
npm run test:api
```

Generate an HTML report:

```bash
npm run test:report
```

## 9. CI/CD with GitHub Actions

The workflow located at .github/workflows/api-tests.yml runs on push and pull_request events targeting main. It installs Node.js, installs dependencies, executes the Newman collection, and uploads the HTML report artifact when available.

## 10. QA Practices Demonstrated

- Test design for positive and negative scenarios
- Smoke coverage for critical API paths
- Functional validation of REST responses
- Contract-style checks for response shape and types
- Query parameter validation
- Repeatable execution with Newman
- CI/CD automation with GitHub Actions
- Documentation written for interview-ready portfolio presentation

## 11. Author

Prepared by Gabriel Souza.

This repository is intended as a QA portfolio example for API testing interviews and professional discussion.