# HttpClient
HttpClient is Angular’s built-in tool to send HTTP requests  
Angular does NOT enable HTTP by default, You MUST import it.

For NgModules (older style) :-
```ts
// app.module.ts
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  imports: [
    HttpClientModule
  ]
})
export class AppModule {}
```

For Standalone :-
```ts
// main.ts or app.config.ts:
import { provideHttpClient } from '@angular/common/http';

providers: [
  provideHttpClient()
]
```
---
### 2. Using in components :-  
Import and inject
```ts
import { HttpClient } from '@angular/common/http';

export class AppComponent {
  constructor(private http: HttpClient) {}
}
```
---

### 3. Making API Call
```ts
this.http.get('https://jsonplaceholder.typicode.com/users')
  .subscribe(data => {
    console.log(data);
  });
```
---
### <center> OBSERVABLE
`this.http.get('/users')` returns an observable
Lifecycle -
1. next (Success)
2. error (Failure)
3. complete (Finished)

```ts
this.http.get('/users').subscribe({
  next: (data) => console.log(data),
  error: (err) => console.log(err),
  complete: () => console.log('done')
});
```

---

```ts
this.http.get<User[]>('/users')
```
User[ ] = array of User objects  
TypeScript now KNOWS structure

---
### <center> METHODS

#### 1. GET
```TS
this.http.get('/users')
  .subscribe(data => console.log(data));
```

#### 2. POST
```ts
this.http.post('/users', {
  name: 'Ayush'
}).subscribe(res => console.log(res));
```