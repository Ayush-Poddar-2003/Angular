# Error Handling
In real world, APIs can fail due to:  
Network issue, Server down, Wrong request, Unauthorized (401), Not found (404)

Basic error handling :-
```ts
this.http.get('/users').subscribe({
  next: (data) => {
    console.log('Success:', data);
  },
  error: (err) => {
    console.log('Error:', err);
  }
});
```

### Error Object :-
```ts
error: (err) => {
  console.log(err.status);   // 404, 500 etc.
  console.log(err.message);  // error message
}
```
---
### Showing in UI
```ts
errorMessage = '';

this.http.get('/users').subscribe({
  next: (data) => {
    this.users = data;
    this.errorMessage = '';
  },
  error: (err) => {
    this.errorMessage = 'Failed to load users';
  }
});
```
```html
<div *ngIf="errorMessage">
  {{ errorMessage }}
</div>
```

---
### Using RxJS catchError
Instead of handling error inside subscribe:
