# Execution Guide

## Run with Postman

1. Open Postman.
2. Import the collection from postman/jsonplaceholder-api-tests.postman_collection.json.
3. Import the environment from postman/jsonplaceholder-environment.postman_environment.json.
4. Select the JSONPlaceholder Environment.
5. Run the full collection or individual folders from the Collection Runner.

## Run with Newman

Install the project dependencies first:

```bash
npm install
```

Run the API test suite:

```bash
npm test
```

Run Newman directly:

```bash
npm run test:api
```

Generate the HTML report:

```bash
npm run test:report
```

The HTML report is written to reports/newman-report.html.

## Run with GitHub Actions

The workflow at .github/workflows/api-tests.yml runs automatically on push and pull_request events targeting main.

What the workflow does:

- Checks out the repository.
- Installs Node.js.
- Installs dependencies.
- Runs the Newman suite.
- Generates an HTML report.
- Uploads the report as a workflow artifact.

## Important Note About JSONPlaceholder

JSONPlaceholder is a fake REST API. Create, update, and delete requests return realistic responses, but they do not modify a persistent backend. For that reason, the suite validates response behavior, not actual data persistence.
