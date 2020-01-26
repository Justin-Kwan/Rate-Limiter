A simple and reusable request rate-limiting microservice that protects external applications' endpoints.

## Features
- Rate-Limiter is light-weight microservice meaning it can be easily distributed and reused
- Rate-Limiter uses a straight-forward fixed window counting implementation
- Rate-Limiter is stateless, clients can choose specific configurations for windows, request limits, etc
- Rate-Limiter provides GRPC access to it’s API, resulting in faster message transmissions and rigourous contracts
- User key value records are cached in Redis




