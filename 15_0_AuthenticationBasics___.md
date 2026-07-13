# Basics -
**Authentication ?** :  
Who, For eg Which employee can enter office  

**Authorization ?** :  
What can you do, Which rooms you can enter

The application verifies the user's identity.

---
### Session-Based Authentication (Old Way)
```
User Login
    |
Server Creates Session
    |
Session ID Generated
    |
Browser Stores Cookie
```

Every request, Browser sends cookie, server checks session

For large applications:
Server must remember every user session  
=> Huge memory consumption

---
### Token-Based Authentication (Modern Way)

```
Login
   |
Backend validates
   |
Creates Token
   |
Token returned
   |
Frontend stores token
```
Now every request sends token.

---

### Common Architecture

```
core
 ├── auth
      ├── services
      │     └── auth.service.ts
      │
      ├── guards
      │     └── auth.guard.ts
      │
      ├── interceptors
      │     └── auth.interceptor.ts
      │
      ├── models
      │     └── auth.model.ts
      │
      └── pages
            ├── login
            └── logout
```
