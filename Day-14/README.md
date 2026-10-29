# Day 14: API Testing & Postman Automation

## 1. API Testing Basics

- **API:** lets two software applications communicate.
- **API testing:** checks an API's response, data, and errors.
- **REST:** an API style commonly used with HTTP.
- **SOAP:** a protocol commonly using XML messages.

### API request and response

```text
Client / Postman
      |
      | HTTP request
      v
    API Server
      |
      | HTTP response
      v
Client checks status, headers, body, and response time
```

## 2. HTTP Methods

| Method | Short definition |
|---|---|
| `GET` | Read data |
| `POST` | Create or submit data |
| `PUT` | Replace a resource |
| `PATCH` | Update part of a resource |
| `DELETE` | Delete a resource |

## 3. Common Status Codes

| Code | Short definition |
|---|---|
| `200` | Request succeeded |
| `201` | Resource created |
| `400` | Invalid request |
| `401` | Authentication required |
| `404` | Resource not found |
| `500` | Server error |

The expected status code depends on the API documentation.

## 4. Postman Setup

1. Create a workspace.
2. Create a collection named `Day14 API Testing`.
3. Create an environment named `Day14 Environment`.
4. Add variables such as `baseUrl` and `resourceId` when needed.
5. Save requests in the collection.
6. Export the collection and environment as JSON files.

### Request workflow

```text
Create Workspace
       |
       v
Create Collection
       |
       v
Create Environment + Variables
       |
       v
Add Requests and Tests
       |
       v
Run Collection and Review Results
```

## 5. Request Parts

A request can contain a method, URL, parameters, headers, authorization, and a body.

```text
Request
 ├── Method + URL
 ├── Parameters
 ├── Headers / Authorization
 ├── Body (when required)
 └── Tests
       |
       v
Response: Status + Headers + Body + Time
```

Example JSON body:

```json
{
  "name": "Test User",
  "job": "QA Engineer"
}
```

## 6. Postman Test Scripts

### Check status code

```javascript
pm.test("Status is 200", function () {
    pm.response.to.have.status(200);
});
```

### Check response time

```javascript
pm.test("Response is under 2 seconds", function () {
    pm.expect(pm.response.responseTime).to.be.below(2000);
});
```

### Check a response field

```javascript
pm.test("Response has an id", function () {
    const body = pm.response.json();
    pm.expect(body).to.have.property("id");
});
```

### Save a variable

```javascript
const body = pm.response.json();
pm.environment.set("resourceId", body.id);
```

Use `{{resourceId}}` in a later request when the API returns an ID.

### Check JSON schema

```javascript
const schema = {
    type: "object",
    required: ["id"],
    properties: {
        id: { type: ["number", "string"] }
    }
};

pm.test("Response matches schema", function () {
    pm.response.to.have.jsonSchema(schema);
});
```

Adjust the schema to match the API's actual response.

## 7. API Testing Types

- **Functional testing:** checks that the API works as expected.
- **Validation testing:** checks required fields and data formats.
- **Negative testing:** checks responses to invalid input.
- **Security testing:** checks authentication and permissions on authorized systems.
- **Load testing:** checks behavior under high traffic; response-time checks alone are not load testing.

## 8. Request Chaining

```text
POST: Create resource
        |
        v
Check response and extract ID
        |
        v
Save ID as environment variable
        |
        v
GET / PUT / PATCH using saved ID
        |
        v
DELETE resource if supported and safe
```

1. Send a create request.
2. Check its response.
3. Save the returned ID in an environment variable.
4. Use that ID in a later request if supported.
5. Delete test data only when safe and allowed.

Some public demo APIs simulate changes instead of saving them.

## 9. Create 50+ Test Requests

| Test group | Suggested number |
|---|---:|
| GET requests | 10 |
| POST requests | 10 |
| PUT/PATCH requests | 10 |
| DELETE requests | 5 |
| Negative and validation tests | 10 |
| Chaining and data-driven tests | 5 |
| **Total** | **50** |

Give every request a clear name and add relevant assertions. Do not copy the same request just to reach 50.

## 10. Data-Driven Testing

```text
CSV / JSON test data
        |
        v
Postman Collection Runner
        |
        v
Run request once per data row
        |
        v
Review each iteration's result
```

1. Create a CSV or JSON file with test data.
2. Open Postman's Collection Runner.
3. Select the collection and data file.
4. Use variables such as `{{username}}` in requests.
5. Run the tests and review each result.

Example CSV:

```csv
username,password
test_user,test_password
invalid_user,wrong_password
```

Use values appropriate for the API being tested.

## 11. Run with Newman

```text
Export Postman Collection + Environment
                 |
                 v
          Newman CLI command
                 |
                 v
          Execute API requests
                 |
                 v
       View results / save report
```

Install Node.js, then install Newman:

```bash
npm install -g newman
```

Run an exported collection:

```bash
newman run postman/Day14-API-Testing.postman_collection.json
```

Run with an environment:

```bash
newman run postman/Day14-API-Testing.postman_collection.json -e postman/Day14-Environment.postman_environment.json
```





