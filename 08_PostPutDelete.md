# API

Js can't be connected directly to your DB, as they executes on browser not on server
 
We have Server side scripting languages like java, python, node they can execute on server, we connect them with DB => Creates API

![alt text](image-27.png)

An API allows your Angular frontend to talk to a backend server.

---
# HTTP Client
Angular provides a built‑in service called: HttpClient

It handles:  
API calls, JSON conversion, Errors, Observables (streamed responses)

>  Import HttpClientModule


GET: “Give me data”  
### POST :  
“Here is some data — save it”  
Used for: Login, Signup, Create user, Submit form, Save data to DB etc.

`this.http.post(URL, DATA)`