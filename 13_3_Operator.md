# <CENTER> OPERATORS

### <center>1. Map
> map is used to transform each value emitted by an observable

👉 Observable gives value  
👉 map changes it

```ts
import { of, map } from 'rxjs';

of(1, 2, 3)
  .pipe(
    map((value) => value * 2)
  )
  .subscribe(console.log);

//2
//4
//6
```
`pipe( )` is used to apply operators like map, filter

> map does NOT change original data it returns transformed values

---
### <center> 2. Filter
> To allow only certain values and ignore the rest

```ts
import { of, filter } from 'rxjs';

of(1, 2, 3, 4, 5)
  .pipe(
    filter((value) => value % 2 === 0)
  )
  .subscribe(console.log);
```

---
### <center> 3. switchMap
Sometimes one async task depends on another.  
switchMap is used to switch from one observable to another

First observable gives value, Then we use that value to start another observable

```js
of(1, 2, 3).pipe(
  switchMap((value) => {
    return of(value * 10); 
    //returning new variable each time
  })
).subscribe(console.log);
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
``
```
`getUser()` : emits user object, like `{ id: 10, name: "Ayush" }`  

`switchMap(user => getOrders(user.id))` :  
For that user:  extract user.id & call new API: `getOrders`  
`switchMap` It switches from:
user observable → orders observable

---
### Real Example (Search box)
User types fast:

    "a" → API call  
    "ab" → API call  
    "abc" → API call

👉 Without switchMap:  
all requests run ❌ (waste)

👉 With switchMap:  
old ones canceled ❌
only latest runs ✅