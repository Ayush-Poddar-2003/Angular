# JWT
JSON Web Token

> It is a compact string used to securely transfer user identity and authorization information between the client and server.

---
### Why JWT Was Created ?
Imagine millions of users.  

**Session Based Storage** : Server stores each user's session.  
**Problems**: High memory usage, Difficult scaling, Server must remember every user

**JWT-Based Authentication**  
**Stateless Authentication :** Server doesn't need to remember users' sessions.

Also hard to send username password with every request.

---

### JWT Structure
`HEADER.PAYLOAD.SIGNATURE`

1. **Header**: contains metadata. 
    ```json
    {
      "alg": "HS256",
      "typ": "JWT"
    }
    // alg = Algorithm Used
    // typ = JWT
    ```

2. **Payload**: Contains user data.  
`{  
  "userId": 1,  
  "name": "Ayush",
  "role": "Admin"
}`   
This data is called **Claims** i.e. Information stored inside token.
3. **Signature** : Used to detect & prevent token hamepring.  
Backend takes: `Header+Payload+Secret Key` & generates 
Signature.  
Secret key exists only on server, Frontend never sees it.  
The most critical security part, as in token, someone can easily change role to admin, what then -> token rejected

---
### Common JWT Claims (Payload data)
1. sub (Subject): User identifier.
2. iat (Issued At) : When token was created.
3. exp (Expiration) : When token expires.
4. role : Used for authorization.
5. iss (Issuer) : Who created token.
6. aud (Audience) : Who should use token.

> JWT is usually Encoded not encrypted,
Anyone can decode payload.

```json
{
  "sub": "1",
  "name": "Ayush",
  "email": "ayush@gmail.com",
  "role": "Admin",
  "iat": 1710000000,
  "exp": 1710003600
}
```
---

## Bearer ?
You'll frequently see:  
`Authorization: Bearer TOKEN`

Bearer means Whoever possesses this token is the authenticated user.

---
> JWT should not live forever.
```json
{
  "exp": 1710000000
}
```

---
# <center> Refresh Token
Imagine relogin after token expiry everytime,  
A Refresh Token is a long-lived token used to generate new Access Tokens without asking the user to login again.

Access Tokens :-
1. Used for API calls
2. Short lifespan
3. Sent with every request

Flow :-
1. Login success: Access Token & Refresh Token returned.
2. Angular sends: Authorization: Bearer ACCESS_TOKEN
3. Access Token expires, Angular calls: POST /refresh-token
4. Backend verifies Refresh Token, and sends new access token.