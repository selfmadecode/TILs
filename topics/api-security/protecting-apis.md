# How to prOtect an API

## Enforce HTTPS
If you deploy your APIs over HTTP, the data is not encrypted and is sent as plain text. You don’t want to send insecure data that could be changed or tampered with. This is where HTTPS comes in. HTTPS stands for **Hypertext Transfer Protocol Secure**.  

With HTTPS, your data is encrypted before it is sent out. This makes it safer. An extra layer called TLS (Transport Layer Security) is added to HTTP to make sure your data is secured.  

**Here's how it works:** The client and server agree on a secure connection, then all data sent between them is encrypted. Even if someone intercepts it, they cannot read it.


## Use Authentication (OAuth2, JWT)
Enforcing HTTPS alone is not enough. Anyone on the internet can call a public API. You want to make sure that only verified users can make calls to your API.  

There are ways to do this:  
- **JWT (JSON Web Token)**: Issue a token to a user after they log in. The user includes this token in every request to prove they are verified.  
- **OAuth2**: Often used by bigger systems to allow secure access without sharing passwords.  

**Here's how it works:** The API checks the token every time a request comes in. If it’s valid, the request continues. If not, it is rejected.


## Authorization
Even if a user is authenticated, they might not be allowed to do everything. This is where **authorization** comes in. It decides what an authenticated user can do.  

Think of authentication as **permission to enter a building**, and authorization as **the key to open only specific rooms inside**.


## Add Rate Limiting and Throttling
APIs can get overwhelmed if too many requests come in at once. Rate limiting stops users from making too many requests in a short time. Throttling slows down requests if they exceed the allowed limit.  

This prevents abuse, DoS attacks, and helps keep your API stable. You can implement this using an **API Gateway** or middleware.
Checkout this Repository for a [rate limit nuget package](https://github.com/selfmadecode/Throttlr.Api.RateLimit)


## Input Validation
Never ever trust a user input. Validate everything coming into your API to make sure it is correct, safe, and expected.  

For example:  
- Check types (string, number, etc.)  
- Check lengths and ranges  
- Sanitize text to prevent attacks like SQL Injection or XSS  

SQL injection means sending malicious commands to a database via an API requests.


## Log and Monitor Suspicious Activity
Keep logs of API requests and monitor them for unusual activity. Logs help you:  
- Track failed login attempts  
- Detect abuse or attacks  
- Debug problems  

You can set up alerts to notify you when suspicious patterns appear.


## Security Audit
Regularly review your API security. Check for:  
- Weak authentication and authorization  
- Vulnerable dependencies or libraries  
- Data exposure  
- Misconfigured servers  

A security audit ensures your API stays safe as it grows and changes.

## Visual Summary

   ┌──────────────┐
   │  Client/API  │
   └─────┬────────┘
         │ HTTPS
         ▼
   ┌──────────────┐
   │   Firewall   │
   │ Rate Limit   │
   │ Throttling   │
   └─────┬────────┘
         │ Auth
         ▼
   ┌────────────────┐
   │ Authentication │
   │  (JWT/OAuth2)  │
   └─────┬──────────┘
         │ Authorization
         ▼
   ┌──────────────────┐
   │ Input Validation │
   │ Logging & Audit  │
   └─────┬────────────┘
         │
         ▼
   ┌──────────────┐
   │    API Logic │
   └──────────────┘


## API Security Cheat Sheet

| Step                         | Purpose / Why it Matters                              |
|------------------------------|-------------------------------------------------------|
| HTTPS                        | Encrypts data, prevents tampering                     |
| Authentication (JWT/OAuth2)  | Ensures only verified users can access your API       |
| Authorization                | Controls what each user is allowed to do              |
| Rate Limiting & Throttling   | Prevents abuse, keeps API stable                      |
| Input Validation             | Protects from bad or dangerous user input             |
| Logging & Monitoring         | Detects suspicious activity and helps debugging       |
| Security Audit               | Regularly checks for weaknesses and risks             |