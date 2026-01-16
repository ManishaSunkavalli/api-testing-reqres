# ReqRes API Test Cases

## 1. GET Users – List Users

### TC_API_001 – Fetch users with valid page number
- Method: GET
- Endpoint: /api/users?page=2
- Expected Status Code: 200
- Validation:
  - Response contains user list
  - Each user has id, email, first_name, last_name

### TC_API_002 – Fetch users with invalid page number
- Method: GET
- Endpoint: /api/users?page=abc
- Expected Result:
  - API handles invalid input gracefully
  - No 5xx server error

### TC_API_003 – Fetch users with non-existing page
- Method: GET
- Endpoint: /api/users?page=999
- Expected Result:
  - Empty data array
  - Valid response structure

---

## 2. GET Single User

### TC_API_004 – Fetch existing user
- Method: GET
- Endpoint: /api/users/2
- Expected Status Code: 200
- Validation:
  - Correct user data returned

### TC_API_005 – Fetch non-existing user
- Method: GET
- Endpoint: /api/users/23
- Expected Status Code: 404

