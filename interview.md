1. Scenario: Slow API Response

Q: Your FastAPI endpoint suddenly becomes slow in production. How will you diagnose it?
Follow-ups:
– How do you check whether the issue is DB latency or code latency?
– How do you use async to improve performance here?

2. Scenario: High Memory Usage

Q: Your Python API is consuming high memory after multiple requests. What steps will you take to find and fix the memory leak?
Follow-ups:
– Which profiling tools will you use in Python?
– What patterns in FastAPI code can cause leaks?

3. Scenario: Concurrent Requests

Q: API gets 1k requests per second. How would you scale FastAPI to handle this?
Follow-ups:
– Why use gunicorn + uvicorn workers?
– How many workers would you choose?

4. Scenario: Long Running Task

Q: You have a task that takes 5 minutes. How do you execute it without blocking API responses?
Follow-ups:
– Why use Celery/RQ/background tasks?
– How do you notify users when task completes?

5. Scenario: File Upload 2GB

Q: Your client uploads a 2GB video. How do you handle large file uploads in FastAPI?
Follow-ups:
– Why use streaming instead of saving directly?
– How do you handle upload interruption?

6. Scenario: API Timeout

Q: Your API must respond within 2 seconds but external API takes 6 seconds. How do you handle it?
Follow-ups:
– How do you implement async timeout?
– How do you design a fallback response?

7. Scenario: Authentication Failure

Q: JWT authentication randomly fails for some users. What would you check?
Follow-ups:
– Could it be a clock drift issue?
– How do you implement token refresh safely?

8. Scenario: Authorization Levels

Q: You need user roles: admin, seller, customer. How do you implement role-based access in FastAPI?
Follow-ups:
– How do you protect endpoints dynamically?
– What if roles need to be updated without redeploy?

9. Scenario: Race Conditions

Q: Two requests update the same row simultaneously. How do you avoid race conditions?
Follow-ups:
– When do you choose optimistic locking?
– How do you use transactions?

10. Scenario: Query Optimization

Q: A DB query takes 10 seconds. How will you optimize it from API side?
Follow-ups:
– How do you cache queries?
– When to denormalize?

11. Scenario: Pagination

Q: You need to show 10 lakhs records. How will you design pagination?
Follow-ups:
– Offset vs cursor pagination?
– Why cursor is faster?

12. Scenario: API Versioning

Q: Your API has breaking changes. How do you handle versioning?
Follow-ups:
– How long do you maintain old versions?
– How to route requests to different versions?

13. Scenario: Multiple Response Types

Q: You must return JSON to web and XML to mobile. How do you handle content negotiation?
Follow-ups:
– How do you auto-detect client type?
– How do you test this?

14. Scenario: Logging

Q: You need full request-response logging in production. How?
Follow-ups:
– How to avoid logging passwords?
– How to log only errors?

15. Scenario: 3rd Party API Failure

Q: Your API depends on a payment API that fails often. How do you handle reliability?
Follow-ups:
– Circuit breaker pattern?
– Retry with exponential backoff?

16. Scenario: WebSockets

Q: You need live order status updates. How do you design a WebSocket endpoint?
Follow-ups:
– How do you handle disconnects?
– How to scale WebSockets?

17. Scenario: Caching

Q: Your API repeatedly calculates a heavy operation. How do you cache it?
Follow-ups:
– Why Redis over in-memory?
– How long will you cache?

18. Scenario: Rate Limiting

Q: Implement rate limiting for login endpoint.
Follow-ups:
– Why Redis?
– How to handle IP spoofing?

19. Scenario: CI/CD Deployment

Q: Your update breaks production. What is your rollback approach?
Follow-ups:
– How do you use blue-green deployment?
– How to rollback DB migrations?

20. Scenario: Schema Validation

Q: Your input body is inconsistent. How do you validate using Pydantic?
Follow-ups:
– How to add custom validators?
– How to handle optional fields?

21. Scenario: API Documentation

Q: How do you customize Swagger UI for better readability?
Follow-ups:
– How to hide internal APIs?
– How to add JWT authentication?

22. Scenario: SQL Injection

Q: A security team reports SQL injection risk. What do you do?
Follow-ups:
– What is parameterized query?
– How to validate user input?

23. Scenario: Data Migration

Q: You add a new DB column. How to migrate without downtime?
Follow-ups:
– How do you use Alembic?
– How do you handle backward compatibility?

24. Scenario: API Gateway

Q: You deploy ESB or API gateway. What changes in FastAPI?
Follow-ups:
– Do you still keep authentication in FastAPI?
– How to secure internal APIs?

25. Scenario: Multiple Database Connections

Q: Your application needs 2 different DB connections. How to manage?
Follow-ups:
– How to handle connection pooling?
– How to switch DB based on tenant?

26. Scenario: Background Scheduler

Q: You need a cron job inside FastAPI. How to implement it?
Follow-ups:
– Why is APScheduler risky inside web worker?
– How to use external scheduler?

27. Scenario: Dependency Injection

Q: How do you share DB session across routes?
Follow-ups:
– Why use Depends()?
– How to close session safely?

28. Scenario: Multipart Request

Q: Upload JSON + file together. How do you parse it in FastAPI?
Follow-ups:
– What are form-data limits?
– How to validate file type?

29. Scenario: Distributed System

Q: Your API runs on 5 servers. How do you maintain user sessions?
Follow-ups:
– Why store sessions in Redis?
– How to avoid session fixation?

30. Scenario: Bad Deployment

Q: You deployed FastAPI with 1 worker. Why is it wrong?
Follow-ups:
– Why use multiple workers?
– How to pick worker type (sync/async)?

31. Scenario: Circular Imports

Q: Your FastAPI project breaks due to circular imports. How do you fix?
Follow-ups:
– What is factory pattern?
– Why separate routers?

32. Scenario: Real-time Data Processing

Q: Client wants real-time logs from server. How do you implement it?
Follow-ups:
– SSE vs WebSocket difference?
– Which scales better?

33. Scenario: Queue-Based Processing

Q: Payment webhook API receives 1 million hits. How do you design?
Follow-ups:
– Why push to queue first?
– How to ensure idempotency?

34. Scenario: ETL API

Q: API triggers an ETL job. How do you handle large data?
Follow-ups:
– Why use streaming?
– How to handle partial failures?

35. Scenario: Duplicate Requests

Q: User accidentally submits order twice. How do you prevent duplicates?
Follow-ups:
– How to use idempotency keys?
– Why database unique constraints?

36. Scenario: Broken JSON Body

Q: API receives malformed JSON. How do you give better error response?
Follow-ups:
– How to override exception handlers?
– How to log malformed JSON?

37. Scenario: Server Crash

Q: FastAPI crashes due to unhandled exception. How do you design global error handling?
Follow-ups:
– How do you handle 422 errors?
– Should stack trace be returned?

38. Scenario: Multi-tenant App

Q: API must support multiple clients with different DBs.
Follow-ups:
– How do you select DB per request?
– How do you isolate customer data?

39. Scenario: Upload Validation

Q: Only allow images under 5MB.
Follow-ups:
– How to validate MIME type?
– How to prevent malicious files?

40. Scenario: Throttling Admin

Q: Admin APIs need no rate limit but user APIs need heavy limit.
Follow-ups:
– How to differentiate client types?
– How to avoid bypassing?

41. Scenario: Bulk Insert

Q: You need to insert 50k rows.
Follow-ups:
– Why use batch insert?
– How to handle partial success?

42. Scenario: API Security Audit

Q: Auditor finds your API leaking stack traces.
Follow-ups:
– How do you hide exception messages?
– How do you enable secure logging?

43. Scenario: HTTPS Enforcement

Q: API must block all HTTP traffic.
Follow-ups:
– How to enforce behind Nginx?
– How to redirect automatically?

44. Scenario: Webhook Retries

Q: Third-party sends same webhook multiple times.
Follow-ups:
– How do you detect duplicates?
– How do you sign webhook events?

45. Scenario: Heavy JSON Serialization

Q: JSON response is 50MB.
Follow-ups:
– Why use ORJSONResponse?
– How to compress responses?

46. Scenario: Soft Delete

Q: You need soft delete instead of permanent delete.
Follow-ups:
– How to hide soft-deleted records?
– How to restore deleted data?

47. Scenario: Debug vs Production

Q: Your API behaves differently in debug mode.
Follow-ups:
– Why never use debug in production?
– How to use .env for config?

48. Scenario: API Performance Testing

Q: You need to benchmark an endpoint.
Follow-ups:
– How do you use Locust/JMeter?
– What performance metrics matter?

49. Scenario: ORM vs Raw Query

Q: ORM query is slow.
Follow-ups:
– Why raw SQL may be faster?
– How to keep ORM + raw hybrid?

50. Scenario: Microservices

Q: You split monolith into microservices.
Follow-ups:
– How do you handle distributed transactions?
– How do you handle network failures?