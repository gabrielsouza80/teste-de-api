# Test Scenarios

| Test Case ID | Endpoint | Method | Scenario | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- |
| TS-001 | /posts | GET | Retrieve the full list of posts | Return 200 and a non-empty array of posts | High |
| TS-002 | /posts/{id} | GET | Retrieve one valid post | Return 200 and an object with id, userId, title, and body | High |
| TS-003 | /posts/{id}/comments | GET | Retrieve comments for a valid post | Return 200 and an array of comments with postId matching the path parameter | High |
| TS-004 | /comments?postId={id} | GET | Filter comments by postId | Return 200 and only comments for the selected postId | High |
| TS-005 | /posts | POST | Create a new post with valid payload | Return 201 and a JSON object containing id, title, body, and userId | High |
| TS-006 | /posts/{id} | PUT | Replace a post with valid payload | Return 200 and an object with the updated resource data | High |
| TS-007 | /posts/{id} | PATCH | Partially update a post | Return 200 and an object with the patched field updated | High |
| TS-008 | /posts/{id} | DELETE | Delete a valid post | Return 200 and an empty JSON object | Medium |
| TS-009 | /users | GET | Retrieve the full list of users | Return 200 and a non-empty array of users | High |
| TS-010 | /users/{id} | GET | Retrieve one valid user | Return 200 and an object with user profile data | High |
| TS-011 | /users/{id}/todos | GET | Retrieve todos for a valid user | Return 200 and an array where each todo belongs to the selected user | High |
| TS-012 | /todos?completed=true | GET | Filter todos by completion flag | Return 200 and only todos with completed=true | High |
| TS-013 | /todos?completed=invalid | GET | Send an invalid filter value | Return 200 and an empty array or other safe response without a server error | Medium |
| TS-014 | /posts | POST | Submit an incomplete payload | Return 201 because JSONPlaceholder accepts the request without strict validation | Medium |
| TS-015 | /posts | GET | Validate response contract for list items | Each item should expose the expected fields and data types | High |
| TS-016 | /users/{id} | GET | Validate nested user contract | Address and company objects should exist with expected nested fields | High |
