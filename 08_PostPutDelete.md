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