## <center> - Route Parameters -
Dynamic values in the URL that Angular can capture and use inside a component, Route parameter = variable inside URL

```ts
{ path: 'user/:id', component: UserComponent }
// :id is a placeholder (dynamic part)
```
Works for: ` /user/anything`, `/user/1`, `/user/69`

---
**NAVIGATION having router params :-**
1. Using routerLink (HTML)
    ```HTML
    <a [routerLink]="['/user', 10]">User</a>
    ```
2. Using Ts (navigate( ))
   ```ts
   this.router.navigate(['/user', 10]);
   ```

---
### <center> - Reading Route Param -

**Step 1**: Import & Inject ActivatedRoute
```ts
import { ActivatedRoute } from '@angular/router';

constructor(private route: ActivatedRoute) {}
```

**What is ActivatedRoute?**  
It gives information about the current route  
👉 Includes: params, query params, route data

**Step 2**: Read the parameter, Two ways:-
  1. **Using snapshot :-**
      ```ts
      ngOnInit() 
      {
        const id = this.route.snapshot.paramMap.get('id'); 
        
        console.log(id); // id="10"
      }
      ```
      `paramMap.get( )` always returns string.   
      `snapshot` = “take value once when component loads”


  2. **Using Observable :-**
      ```ts
      ngOnInit() {
        this.route.paramMap.subscribe(params => {
          const id = params.get('id');
          console.log(id);
        });
      }
      ```
      It is listening continuously, where as snapshot = one-time read
---
## <center> - Query Parameters -
Extra data added to the URL after `?`
```rust
/route?key1=value1&key2=value2

Eg:-
/home?name=ayush&age=25
```

- `/home` → route path
- `?name=ayush&age=25` → query parameters

Route param = identifies resource  
Query param = modifies behavior  

Query params do NOT change component

**USES :-**  
The same component stays active &  
Only filtering / sorting / searchin / extra options changes

**NAVIGATION :-**
1. Using HTML   
   ```html
   <a
    [routerLink]="['/home']" 
    [queryParams]="{ name: 'ayush', age: 25 }">
   </a>
   ```
   Result : `/home?name=ayush&age=25`

2. Using Ts
    ```ts
    this.router.navigate(['/home'], {
      queryParams: { name: 'ayush', age: 25 }
    });
    ```

### <center> - READING QUERY PARAMS FROM URL -

Step 1: Importing and injecting ActivatedRoute
```ts
import { ActivatedRoute } from '@angular/router';

constructor(private route: ActivatedRoute) {}
```

For eg: `/home?name=ayush&age=25`

Step 2 : Either
  ```ts
ngOnInit() {
  const N = this.route.snapshot.queryParamMap.get('name');
  const A = this.route.snapshot.queryParamMap.get('age');

  console.log(N, A);
}
  ```

```ts
ngOnInit() {
  this.route.queryParams.subscribe(params => {
    console.log(params['category']);
    console.log(params['page']);
  });
}
```
---
