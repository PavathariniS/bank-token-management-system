# API Documentation

This document lists the planned API endpoints for the Smart Bank Token Management System.

## Customer APIs

### POST /api/customers
Create a new customer profile.

Request body:
```json
{
  "name": "John Doe",
  "phoneNumber": "9876543210"
}
```

### GET /api/customers/{id}
Fetch one customer.

## Token APIs

### POST /api/tokens
Generate a token for a customer.

Request body:
```json
{
  "customerId": 1,
  "serviceId": 2,
  "priorityLevel": "NORMAL"
}
```

### GET /api/tokens/{id}
Fetch token details.

### GET /api/tokens/waiting
Fetch all waiting tokens.

### PUT /api/tokens/{id}/call
Mark token as called.

### PUT /api/tokens/{id}/serve
Mark token as serving.

### PUT /api/tokens/{id}/complete
Mark token as completed.

### PUT /api/tokens/{id}/skip
Skip a token.

## Counter APIs

### GET /api/counters
Get all counters with status.

### PUT /api/counters/{id}/status
Update counter status.

## Staff APIs

### POST /api/staff/login
Staff login.

## Notes
These endpoints are subject to change as the project develops.
