# <center> RxJs
Reactive Extensions for JavaScript.  
It is a library to handle asynchronous data streams

---
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
it PRODUCES values when subscribed ✅


```ts
this.http.get('/api/users');  
//returns observable, future upcoming data
```

```ts
const users = this.http.get('/api/users');
console.log(users);
//Wont work coz, API request has not completed
```

#### Characteristics :-
1. Lazy Execution: Observable does nothing until subscribed
2. Multiple Values Over Time, Unlike Promises
3. Can Emit 3 Types of Signals  
Every Observable can send: next, error, complete
4. Can be cancelled unlike promise.

> When you see $ in Angular:   
It usually means, This is an Observable
---
Syntax :
```ts
import { Observable } from 'rxjs';

const obs$ = new Observable((observer) => {
  // emit values here
});

// Observable → creates the stream
// observer → sends data out
```
---
### Observer Methods :-

1. **next(value)**  :     sends data
    ```ts
    observer.next('A');
    ```
    Can be called multiple times  
    Represents values flowing in the stream

2. **error(error)** : Sends error and stops execution
    ```ts
    observer.error('Something went wrong');
    ```
    After error( ) → stream ends  
    No next( ) or complete( ) after this

3. **complete()**: Marks stream as finished
    ```ts
    observer.complete();
    ```
    After complete() → nothing else runs    
    Normal termination (no error)

> next() goes to either error or complete not both

---
### <center> Subscribe ?
subscribe( ) is used to listen to an Observable and receive its data

For eg;-
```ts
import { Observable } from 'rxjs';

const obs$ = new Observable((observer) => {
  observer.next('A');
  observer.next('B');
  observer.complete();
});
```
When someone subscribes → I will:  
send "A"  
send "B"  
then finish  


```js
obs$.subscribe({
  next: (value) => console.log(value),
  error: (err) => console.log('Error:', err),
  complete: () => console.log('Done')
});

//output
//A
//B
//Done
```
---

### Subscription Object
When we subscribe we get something back
```ts
const sub = obs$.subscribe(...);
sub.unsubscribe();
```




---
### Typing

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