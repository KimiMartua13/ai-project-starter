# api_contracts.md

<!--
This file is generated/re-written by the API Designer.
Context sources: docs/architecture.md + docs/schema.dbml + docs/ui_flow.md
Defines HTTP methods, endpoints, request payloads, response structures, and status codes.
-->

## 1. Unified API Response Envelope (Decoupled Standard)

All backend endpoints must return a consistent JSON envelope so that the frontend can consume responses cleanly:

### Success Response Format (2xx):
```json
{
  "success": true,
  "message": "Operation completed successfully",
  "data": {},
  "meta": {}
}
```

### Error Response Format (4xx / 5xx):
```json
{
  "success": false,
  "message": "Error description message",
  "error": {
    "code": "ERROR_CODE_NAME",
    "details": {}
  }
}
```

---

## 2. API Endpoints Contract

<!--
Format for defining each endpoint:

### [POST] /api/v1/auth/register
- **Description**: Register a new user account
- **Authentication**: None
- **Request Headers**: `Content-Type: application/json`
- **Request Body**:
```json
{
  "name": "string",
  "email": "string (email format)",
  "password": "string (min 8 chars)"
}
```
- **Response 201 Created**:
```json
{
  "success": true,
  "message": "User registered successfully",
  "data": {
    "id": "uuid",
    "name": "string",
    "email": "string"
  }
}
```
- **Response 422 Unprocessable Entity (Validation Error)**:
```json
{
  "success": false,
  "message": "Validation failed",
  "error": {
    "code": "VALIDATION_ERROR",
    "details": {
      "email": ["Email is already registered"]
    }
  }
}
```
-->
