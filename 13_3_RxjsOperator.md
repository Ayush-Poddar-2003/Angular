# <CENTER> OPERATORS

### pipe()
Used to apply operators on an Observable  
Observable → pipe() → transform data → subscribe()

Scenario :-  
Suppose API gives
```ts
{
  name: "Ayush",
  age: 22
}
```

If you want only name  
Without RxJS:
messy logic in subscribe ❌

---
SYNTAX :-
```ts
observable$
  .pipe(
    operator1(),
    operator2()
  )
  .subscribe(...)
```

> Observables are immutable,  pipe gives a new modified stream

---
### <center>1. Map
> map is used to transform each value emitted by an observable

👉 Observable gives value  
👉 map changes it

```ts
import { of, map } from 'rxjs';

of(1,2,3).pipe( map((value)=>value*2) )
  .subscribe(console.log);

//2
//4
//6
```

> map does NOT change original data it returns transformed values

```ts
this.http.get('/api/users')
  .pipe(
    map(response => response.map(person => person.name))
  )
  .subscribe(names => console.log(names));
```

```
API gives → array (response)
↓
RxJS map runs → receives full array
↓
JS map runs → loops each person
↓
extract name
↓
return new array
```


---
### <center> 2. Filter
> filter is used to keep only the values you want,
It removes unwanted data

```ts
import { of, filter } from 'rxjs';

of(1, 2, 3, 4, 5)
  .pipe(
    filter((value) => value % 2 === 0)
  )
  .subscribe(console.log);
```

---

### <center> 3. tap( )
> tap() is used to observe values without changing them

It is mainly used for:  
logging, debugging, checking data etc

```ts
import { of } from 'rxjs';
import { tap } from 'rxjs/operators';

of(1, 2, 3)
  .pipe(
    tap(x => console.log('Inside tap:', x))
  )
  .subscribe(console.log);
```
---

### <center>  4. switchMap 
SwitchMap is used to switch from one observable to another  
First observable gives value, Then we use that value to start another observable

SYNTAX :-
```ts
observable$
  .pipe(
    switchMap(val => newObservable$)
  )
  .subscribe(...)
```

```js
import { of } from 'rxjs';
import { switchMap } from 'rxjs/operators';

of(1, 2)
  .pipe(
    switchMap(x => of(x * 10))
  )
  .subscribe(console.log);

// output
// 10 20
```

Usecase :-
```js
getUser()
  .pipe(
    switchMap(user => getOrders(user.id))
  )
  .subscribe(orders => {
    console.log(orders);
  });
```
`getUser()` :  
emits user object, like `{ id: 10, name: "Ayush" }`  

`switchMap(user => getOrders(user.id))` :  
For that user:  extract user.id & call new API: `getOrders`  

`switchMap` It switches from:
user observable → orders observable

---

### <center> MergeMap
mergeMap runs all inner observables and does NOT cancel anything

switchMap cancels previous ❌  
mergeMap keeps all ✅ 

```ts
import { of } from 'rxjs';
import { mergeMap } from 'rxjs/operators';

of(1, 2)
  .pipe(
    mergeMap(x => of(x, x * 10))
  )
  .subscribe(console.log);

// 1
// 10
// 2
// 20
```

---

## <center> debounceTime?

debounceTime waits for a pause before emitting a value

Usecase, Wait until user stops typing

```ts
import { fromEvent } from 'rxjs';
import { debounceTime } from 'rxjs/operators';

fromEvent(inputBox, 'keyup')
  .pipe(
    debounceTime(1000)
  )
  .subscribe(event => {
    console.log('User stopped typing');
  });
```
User types continuously → nothing happens  
Stops for 1 second → event triggers ✅

---

## <center> catchError
If error happens → catch it → return something else