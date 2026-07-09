# API Test Strategy

## Objective

This strategy describes how the JSONPlaceholder API is validated in a portfolio-ready QA project. The focus is on clarity, repeatability, and interview-friendly test design.

## Scope

The collection covers read and write operations for posts, comments, users, and todos. It includes both standard success paths and selected edge cases that demonstrate how the API behaves when inputs are incomplete or invalid.

## Test Layers

### Smoke Tests

Smoke tests confirm that the most important endpoints are reachable and return the expected HTTP status codes and JSON payloads.

### Functional Tests

Functional checks validate response content, filters, and resource-specific behavior for the required endpoints.

### Positive Scenarios

Positive scenarios use valid IDs, valid filters, and correctly formatted payloads. These cases verify that the API returns the expected structure and data types.

### Negative Scenarios

Negative scenarios intentionally use invalid or incomplete input to show how the API behaves outside the happy path. For JSONPlaceholder, these cases also highlight that the service is a mock API and does not enforce strong server-side validation.

### Contract Checks

Basic contract validation is performed through assertions on required fields, data types, nested objects, arrays, and filtered results. This is a lightweight contract check rather than a full schema-validation approach.

### Regression Testing

The same collection can be rerun after any future change to confirm that core response patterns remain stable.

## Limitations of JSONPlaceholder

JSONPlaceholder is intentionally fake. It simulates CRUD operations but does not persist changes in a real backend. For this reason:

- POST, PUT, PATCH, and DELETE tests validate response behavior rather than true database state changes.
- Some negative cases demonstrate the absence of strict validation instead of a real server-side rejection.
- The API is ideal for learning and portfolio work, but it is not a production system.

## Acceptance Criteria

The suite is considered healthy when:

- Required endpoints return the correct status codes.
- List endpoints return arrays.
- Resource endpoints return objects.
- Query filters return only the expected subset of data.
- Key fields and data types are present in each response.
- Response times stay under the defined threshold in normal conditions.