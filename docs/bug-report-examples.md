# Bug Report Examples

## BUG-001 - POST /posts accepts incomplete payload without validation

**Title**: POST /posts accepts incomplete payload without validation

**Environment**: Postman collection execution against https://jsonplaceholder.typicode.com/

**Severity**: Medium

**Priority**: Medium

**Steps to Reproduce**:
1. Send POST /posts with a payload containing only a title field.
2. Inspect the response.

**Expected Result**: The API should reject the request with a validation error because required fields are missing.

**Actual Result**: The API returns a success response and generates an id.

**Evidence**: Postman request and response showing HTTP 201 with a JSON body.

**Notes**: This is a good portfolio example of a validation gap, but on JSONPlaceholder it should also be treated as a fake-API limitation.

## BUG-002 - DELETE /posts/{id} does not persist the deletion

**Title**: DELETE /posts/{id} does not persist the deletion

**Environment**: Postman collection execution against https://jsonplaceholder.typicode.com/

**Severity**: Low

**Priority**: Low

**Steps to Reproduce**:
1. Send DELETE /posts/1.
2. Repeat GET /posts/1.

**Expected Result**: The post should no longer be returned after deletion.

**Actual Result**: The API returns a successful delete response, but the resource still behaves as available on subsequent reads.

**Evidence**: Sequential Postman requests showing the delete response and the follow-up GET response.

**Notes**: This behavior is expected for JSONPlaceholder because it simulates CRUD operations only.

## BUG-003 - GET /todos?completed=invalid returns no validation message

**Title**: GET /todos?completed=invalid returns no validation message

**Environment**: Postman collection execution against https://jsonplaceholder.typicode.com/

**Severity**: Low

**Priority**: Medium

**Steps to Reproduce**:
1. Send GET /todos?completed=invalid.
2. Inspect the response payload.

**Expected Result**: The API should reject the invalid filter value with a clear validation error.

**Actual Result**: The API returns an empty array without explaining that the filter value is invalid.

**Evidence**: Postman response body showing an empty array and HTTP 200.

**Notes**: Useful as a negative test example and for discussing input validation expectations in an interview.
