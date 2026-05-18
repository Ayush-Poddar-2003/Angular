# Login/Logout Flow

### Login Flow :-
1. User enters email & password
2. Angular sends request to backend:
   ```ts
   POST /loginShow
   ```
3. Backend responds:
    ```json
    {  
        "token": "abc123..."
    }
    ```
4. Angular stores token
5. User is redirected to dashboard


### Logout Flow :-

1. User clicks logout
2. Angular:  
Removes token  
Redirects to login page
3. User becomes unauthenticated

---

# <CENTER> JWT
JSON Web Token  
👉 It is a secure string token sent by the backend after login  
👉 It proves: “This user is authenticated”

Structure of JWT:
`xxxxx.yyyyy.zzzzz`
1. Header : Contains algorithm info  
    ```json
    {
        "alg": "HS256",
        "typ": "JWT"
    }
    ```
2.  Payload : Contains user data
    ```js
    {
        "userId": 123,
        "role": "admin",  
        "email": "admin@test.com",
        "exp": 1716239022
    }
    ```

3. Signature  
Used to verify token (handled by backend)  
👉 Angular does NOT generate or verify signature

---
Flow :-
```
1. User logs in
2. Backend sends JWT
3. Angular stores token
4. Angular sends token in every API request
5. Backend verifies token → allows/denies access
```