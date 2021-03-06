# Rate-Limiter

A simple and reusable request rate-limiting microservice that protects external applications' endpoints.

## Features
- Light-weight microservice which can be easily distributed and reused
- Stateless rate-limiting, where clients can choose specific configurations for time-windows, request limits, etc.
- gRPC access to the API, resulting in faster message transmissions and rigorous contracts
- Redis caching of user key-value records

## Running Locally

Make sure you have Node.js, npm and Redis installed

      # Clone this repo by typing into your terminal
      $ git clone https://github.com/Justin-Kwan/Rate-Limiter
      
      # Change to directory containing index.js file
      $ cd Rate-Limiter/server/src
      
      # Start application
      $ node index.js
      
## Testing Locally
      
      # Change to server directory
      $ cd Rate-Limiter/server
      
      # Start Redis server 
      $ redis-server
      
      # Run tests
      $ npm test
      
 ## gRPC Api Access
 
 Rate-Limiter provides gRPC access via an unary call. The service protocol buffer definitions are:
 
      # rate_limiter.proto
 
      service RateLimiter {
            rpc RateUserLimit (RateLimitRequest) returns (RateLimitResponse) {}
      }

      message RateLimitRequest {
            required string ipAddress = 1;
            required string requestedRoute = 2;
            required int64 requestedServiceId = 3;
            required int64 maxTokens = 4;
            required int64 requestWindow = 5; // time in seconds
      }

      message RateLimitResponse {
            required int64 maxTokens = 1;
            required int64 tokenCount = 2;
      }

 
 
 
 
      
