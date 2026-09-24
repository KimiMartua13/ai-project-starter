# api_contracts.md

<!--
This file is generated/re-written by the API Designer.
Context sources: docs/architecture.md + AGENTS_BACKEND.md + docs/schema.dbml + docs/ui_flow.md
Defines HTTP methods, endpoints, request payloads, response structures, and status codes.
-->

## 1. Unified API Response Envelope (Decoupled Standard)

JSON API responses use the envelope below so that the frontend can consume them consistently. A direct file download is the only default success-response exception described here; its body is the file content, not JSON. An endpoint contract must explicitly identify which response form it uses.

### Success Response Format (2xx):

`success`, `message`, and `data` are required. `meta` is optional: include it only when the endpoint contract defines response metadata (for example, pagination). When present, `meta` must be a JSON object with fields specified by that endpoint. Omit `meta` when no metadata is defined; an empty object is not required.

The following example shows a success response without `meta`. Endpoints that need metadata must define its fields in their own response contract.

```json
{
  "success": true,
  "message": "Operation completed successfully",
  "data": {}
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

### Direct File Download Response

Use this form only when an endpoint sends the file itself. Do not place file bytes, Base64 data, or a file stream inside the JSON `data` field.

| Response | Required contract details |
| :--- | :--- |
| Success | Exact HTTP status, file media type (`Content-Type`), `Content-Disposition: attachment` and the filename or filename-generation rule, and whether the body is the file content. No JSON envelope is sent. |
| Failure before the file response starts | HTTP error status and `Content-Type: application/json`; body follows the Error Response Format above. Do not send a file attachment header with this JSON error. |

For every download endpoint, define its HTTP method and route, authentication/authorization, request parameters, success headers and filename rule, and expected error statuses. The frontend must handle the success as a file and the failure as JSON according to the response status and `Content-Type`; it must not parse a successful file body as JSON. If an endpoint returns a download URL instead of the file itself, that response is JSON and must use the success envelope, with its URL fields defined by the endpoint. This section defines the response pattern only and does not create an export endpoint or select a project file format.

Illustrative CSV download response (not a project endpoint or a required file format):

```http
HTTP/1.1 200 OK
Content-Type: text/csv; charset=utf-8
Content-Disposition: attachment; filename="example.csv"

id,name
1,Example
```

### Responses Without a Body

Do not choose `204 No Content` by default for application endpoints; use a documented JSON success response when the client needs a success result. A `204` response cannot carry the JSON envelope. If a project explicitly requires a bodyless response, its endpoint contract must name the status and state that no body or envelope is sent.

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
