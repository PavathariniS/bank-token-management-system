# Database Design

This project uses MySQL with a clean relational structure.

## Main Tables

### customers
- id (PK)
- full_name
- phone_number
- created_at

### banking_services
- id (PK)
- name
- average_service_minutes
- description

### counters
- id (PK)
- counter_number
- status
- service_id (FK, optional)

### tokens
- id (PK)
- token_number
- status
- priority_level
- customer_id (FK)
- service_id (FK)
- counter_id (FK, optional)
- queue_position
- estimated_wait_minutes
- created_at
- updated_at

### users
- id (PK)
- username
- password_hash
- role
- created_at

## Key Relationships
- One customer can create many tokens.
- One banking service can be linked to many tokens.
- One counter can serve many tokens over time.
- One user can manage the dashboard and queue.

## Design Goals
- Keep tables simple
- Use proper primary and foreign keys
- Avoid storing plain-text passwords
- Keep the schema understandable for a first-year student
