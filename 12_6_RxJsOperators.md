# Operators ?
`this.http.get('/users').subscribe(...)`

What if you want to:  
Transform data, Call another API, Handle errors, Delay input

👉 .subscribe() alone becomes messy

> Operators = tools to modify data BEFORE it reaches subscribe

Observable → pipe(operators) → subscribe()

---
### pipe( )
pipe() is where you apply operators  
`Raw response → pipe → processed response → subscribe`
```ts
this.http.get('/users').pipe(operator).subscribe();
```

---

## <center> map
Transform data  
Example:
API returns:`[{ "id": 1, "name": "Ayush" }]`
```ts
this.http.get('/users').pipe(
  map((users: any) => users[0].name)
).subscribe(name => {
  console.log(name);
});

//Full response → just extracted name
```

## <center> tap
Do something WITHOUT changing data
```ts
this.http.get('/users').pipe(
  tap(data => console.log('API called'))
).subscribe(data => {
  console.log(data);
});
```

### <center> switchMap

Nested API calls are messy
```ts
this.http.get('/users').subscribe(users => {
  this.http.get('/orders').subscribe(orders => {
    // messy
  });
});
```

Solution :-
```ts
this.http.get('/users').pipe(
  switchMap(users => this.http.get('/orders'))
).subscribe(orders => {
  console.log(orders);
});
```
What switchMap does:  
Cancels previous request and switches to new one

---
###  <center>catchError
Handle errors inside pipeline
```ts
this.http.get('/users').pipe(
  catchError(err => {
    console.log('Error handled here');
    return of([]); // fallback value
  })
).subscribe(data => {
  console.log(data);
});
```

---
### <center> debounceTime (Search Optimization)

Delay API call until user stops typing

```ts
search$.pipe(
  debounceTime(500)
).subscribe(term => {
  this.http.get(`/users?name=${term}`).subscribe();
});
``
```