# Architecture Overview

This document explains the system architecture for the Smart Bank Token Management System.

## 1. Layered Design
We are following a simple and beginner-friendly structure:

Controller -> Service -> Repository -> Database

### Controller Layer
Responsibilities:
- Receive HTTP requests
- Validate input
- Pass data to the service layer
- Return HTTP responses

### Service Layer
Responsibilities:
- Handle business logic
- Manage queue rules
- Calculate waiting time
- Validate token lifecycle transitions
- Apply priority rules

### Repository Layer
Responsibilities:
- Talk to MySQL
- Save, update, and fetch entities
- Keep database logic separate from business logic

### Database Layer
Responsibilities:
- Store system data
- Maintain relationships between customers, tokens, counters, and services

## 2. Main Modules
- Customer module
- Token module
- Queue and priority module
- Counter module
- Waiting-time module
- Staff authentication module

## 3. Core Idea
A customer requests a token for a specific service. The system stores the request, assigns a queue position, and calculates an estimated wait time. Staff can then call the next customer, assign them to a counter, and move the token through its lifecycle.

## 4. Why This Architecture Works Well
- Easy to explain in viva
- Easy to test
- Easy to maintain
- Clear separation of responsibilities
- Fits the student learning goal

## 5. Future Improvements
- Add customer login
- Add notifications for token calls
- Add admin analytics dashboard
- Add better waiting-time recalculation
