### Asynchronous (takes time)
Asynchronous = don’t wait, continue other work
 examples :-
```js
fetch('/api/users') // data comes later
```

> How do I represent data that does NOT exist yet, but WILL exist later?  
JavaScript needs a container for future data.

Solutions :-
1. Callbacks ❌ messy
2. Promises ✅ better
3. Observables** ✅ powerful (Angular choice)



---
### <center> Observables ?
A function/process that generates values and sends them


Observable = YouTube channel  
It does NOT store videos for you ❌  
It keeps producing/uploading videos ✅

Observable can get values from:  
API response, User typing, Button click, Timer, Live data (chat, stock price)

So:
Observable produces values using some source

```ts
this.http.get('/api/users');  
//returns observable, future upcoming data
```

```ts
const users = this.http.get('/api/users');
console.log(users);
//Wont work coz, API request has not completed
```

---

### <center> Subscribe ?
subscribe() is used to listen to an Observable and receive its data

```ts
import { Observable } from 'rxjs';

const obs = new Observable((observer) => {
  observer.next(1);
  observer.next(2);
  observer.next(3);
  // next(value): send this value to subscriber  
});
```
```js
obs.subscribe((data) => {
  console.log(data);
});
```
Handles above `next( )` function.    
Other functions :-  
`complete( )`: No more values will come.  
`error( )`: After error( )   Observable stops completely

```js
obs.subscribe({
  next: (data) => console.log(data),
  error: (err) => console.log(err),
  complete: () => console.log("Done")
});
```
Handles:  
`next( )`, `error( )`, `complete( )`

---


Until you subscribe:  
❌ API call does NOT happen
❌ No network request
❌ No data
    


---
### Example :-
```ts
//User Service, we make request here
import { HttpClient } from '@angular/common/http';

@Injectable({
  providedIn: 'root'
})

export class UserService {

  constructor(private http: HttpClient) {}

  getUsers() {
    return this.http.get('API_URL');
  }
}
```
Requesting from the component file
```ts
//home.component.ts
import { Component, OnInit } from '@angular/core';
import { UserService } from '../services/user.service';

@Component({
  selector: 'app-home',
  templateUrl: './home.component.html'
})

export class HomeComponent implements OnInit {

  usersArr: any[] = [];

  constructor(private us: UserService){} //child of service

  ngOnInit() {
    this.us.getUsers().subscribe((data) => {
      this.usersArr = data;
    });
  }
}
```

---

### <center> SUMMARY
```
Observable = future data stream
HttpClient returns Observable
subscribe() starts the request
Data arrives inside subscribe
Services return Observables
Components subscribe
```

---
---


> API → subscribe → store in variable → HTML uses it
```ts
data: any[] = [];

ngOnInit() {
  this.http.get<any[]>('api').subscribe(res => {
    this.data = res;
  });
}
```
```html
<div *ngFor="let item of data">
  {{ item.name }}
</div>
```

---
### New way (Observable + async pipe)

> API → directly to HTML, async handles subscribe automatically

```ts
data$ = this.http.get<any[]>('api');
```
```html
<div *ngFor="let item of data$ | async">
  {{ item.name }}
</div>
```

#### What async pipe does ?

👉 It subscribes for you, gives data to HTML, unsubscribes automatically  
So you don’t write .subscribe() manually