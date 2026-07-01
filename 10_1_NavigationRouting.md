## <center> NAVIGATION
Changing URLs

### <center> 1. routerLink (HTML) -
`routerLink` is a directive that :-  
- Prevents default browser reload,   
- Updates URL internally,  
- Triggers router,  
- Router does the rest, change of component

**Why NOT use href ?**  
Browser performs full page reload, Angular app restarts, State is lost

```TS
// Absolute Path
<a routerLink="/home">Home</a>

// Removes existing path, starts from root
```
```ts
// Relative Path
<a routerLink="home">Home</a>

// Based on your current route, It appends to current path.
```

**ARRAY SYNTAX :-**  
lets you pass dynamic, structured navigation values, query params.  
```HTML
<a [routerLink]="['/home']">Home</a>
```

```html
<a [routerLink]="['/user', user.id]">User</a>

Built URL is like : /user/10
```

---

**Active Link Styling :-**  
It adds a CSS class when the route linked to is currently active
```html
<a routerLink="/about" routerLinkActive="active"> About </a>
```
Applies active CSS class when route matches, for eg  
if want to hightlight current thing in navbar

Works on Nested routes too, To avoid :-
```html
<a
  routerLink="/about" 
  routerLinkActive="active"
  [routerLinkActiveOptions]="{ exact: true }"
>
</a>

/about      → active ✅
/about/team → NOT active ❌
```

---

### <center> 2. Programmatic(ts) | router.navigate() -

Step 1 : Injecting the Router :-
```ts
import { Router } from '@angular/router';

constructor(private router: Router) {}
```


```ts
this.router.navigate(['/user', 10]); //preferred
// OR
this.router.navigateByUrl('/user/10');
```
Relative Navigation :-
```ts
this.router.navigate(['profile'], {
  relativeTo: this.route
});

// If current : /home
// then : /home/profile
```

---
## <center> Navigation Object

When
```ts
this.router.navigate(
  ['home/reports/lifeTime']
);
```

Angular internally creates a navigation object

```ts
{
    id: 25,
    initialUrl: '/home/reports/lifeTime',
    finalUrl: '/home/reports/lifeTime',
    trigger: 'imperative',
    extras: {
        state: undefined
    }
}
```
Now inside Component, if you do: `console.log(this.router.getCurrentNavigation());`  
you'll get that object.

Other Example -
```ts
this.router.navigate(
  ['home/reports/lifeTime'],
  {
      state: {
          username: 'Ayush',
          age: 23
      }
  }
);
```
```ts
{
    id: 26,
    initialUrl: '/home/reports/lifeTime',
    finalUrl: '/home/reports/lifeTime',

    extras: {

        state: {
            username: 'Ayush',
            age: 23
        }
    }
}
```
> this.router.getCurrentNavigation() : returns current object

`this.router.getCurrentNavigation()?.extras`
```ts
{
    state: {
        username: 'Ayush',
        age: 23
    }
}
```
`this.router.getCurrentNavigation()?.extras?.state`
```ts
{
    username: 'Ayush',
    age: 23
}
```