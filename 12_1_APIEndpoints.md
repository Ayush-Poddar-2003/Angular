# API ?
A contract/interface that allows a client to talk to a server  
API = how client is allowed to ask  
API is the exposed layer of the server

You can’t ask anything randomly,  
You can only order what’s on menu like restaurant

API defines what is allowed and how to ask.

---
### ENDPOINT ?
An endpoint is a specific URL inside an API that performs one operation

API = full system  
Endpoint = individual action

API Eg : https://api.example.com

    GET    /users        → get all users
    GET    /users/1      → get one user
    POST   /users        → create user
    DELETE /users/1      → delete user

Each line = one endpoint  
Endpoint = the exact location where request is handled

> API is Collection of Endpoints

Endpoint = Combination of METHOD + URL

---
```ts
this.http.get('/users')
```
What you're doing:  
Calling API, Hitting endpoint, Sending HTTP request, 