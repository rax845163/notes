# Database per service

## Problem
What's the database architecture in a microservice application?

## Conclusion
### Pros and Cons
- Pros:
  - Helps ensure that the services are loosely coupled. Changes to one service’s database does not impact any other services.
- Cons:
  - Distributed transcations are best to be avoided.
  - Complexity of managing multiple SQL and NoSQL databases.

### Solutions for transcations and queries that span services
- Implementing transcations that span services: Saga pattern
- Implementing queries that span services:
  - Api composition:


