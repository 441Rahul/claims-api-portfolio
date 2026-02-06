# Error Model – Claims Processing API

## Error Response Structure
```json
{
  "errorCode": "CLAIM_INVALID_STATE",
  "message": "Claim cannot be approved in current status",
  "timestamp": "2026-02-06T10:30:00Z"
}

## Standard Error Codes

| HTTP Status | Error Code | Scenario |
|------------|-----------|----------|
| 400 | INVALID_REQUEST | Missing or malformed request data |
| 404 | CLAIM_NOT_FOUND | Claim ID does not exist |
| 409 | CLAIM_INVALID_STATE | Invalid lifecycle transition |
| 422 | BUSINESS_RULE_VIOLATION | Business validation failure |
| 500 | INTERNAL_ERROR | Unexpected system failure |


## Error Handling Principles

- Error responses are deterministic and consistent across APIs
- Business rule failures are clearly separated from technical failures
- Error codes are stable and suitable for downstream automation
- HTTP status codes reflect intent, not just failure
