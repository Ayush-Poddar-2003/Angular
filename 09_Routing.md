# <center>Routing

Traditional websites (old-school):

You click a link ->
Browser sends a request to the server ->
Server sends back a new HTML page ->
Browser reloads the whole page

👉 Every click = full page reload

---
BUT Angular apps are Single Page Applications (SPA):  
Only one index.html -> That file is loaded once ->
The browser never reloads the page again

👉 After the first load, everything happens inside the same page.



---

### What Routing ACTUALLY does ?
When the URL changes, Angular routing:

✅ Reads the new URL  
✅ Decides which component matches that URL  
✅ Removes the current component  
✅ Displays the new component  
✅ Keeps the app running (no reload)

---
### Building Blocks of Angular Routing :-

1. Routes (Route Configuration) :  
URL part ↔ Component, describe what should happen
2. Router :  
decides what is active
3. `<router-outlet>` :   
slot in HTML, shows what is active

---
### app.routes.ts :-
```ts
export const routes = [ 
    { path: 'home', component: HomeComponent }
    // ❌ Do NOT write /home
];
```
When this route matches, create this component and display it inside `<router-outlet>`

---
```ts
{ path: '', component: HomeComponent }
```
**Meaning**: URL is / , Nothing after the slash  
This is not a redirect, It directly loads the component.

---
> Route order REALLY matters
```ts
{ path: '', component: HomeComponent }
{ path: 'login', component: LoginComponent }
```
Angular checks:
1. Is URL / ? → Yes → LoadsHomeComponent
2. URL Stays `http://localhost:4200/`
2. Stops checking further, infinite glitch

---
### <center>Default route using REDIRECT

```ts
{ path: '', redirectTo: 'home', pathMatch: 'full' }
```
App opens at /  
URL becomes /home,    
Then loads HomeComponent

---
### pathMatch: 'full' ?
Angular can match routes in two ways:  
1. 'prefix' (default)  
`{ path: ' ', redirectTo: 'home' }`  
Angular interprets / as a prefix of every URL,  
/home, /login etc all starts with /   
Result:
👉 Infinite redirect loop
2. 'full'   
`{ path: '', redirectTo: 'home', pathMatch: 'full' }`: Only redirect when the entire URL is empty.
---

### 404 route ?
`{ path: '**', component: PageNotFoundComponent }`  
✅ The wildcard route MUST be the LAST route.

---
## <center> NAVIGATION
1. Template‑based
2. Programmatic navigation

### <center> - Template Based -
How does a user move between routes 

`routerLink` is a directive that tells Angular:  
“When this element is clicked, update the URL using Angular Router.”

```TS
<a routerLink="/home">Home</a> 
// '/' is used
```

*What happens step‑by‑step ?*

```
1. User clicks the link
2. Angular intercepts the click
3. Browser reload is prevented
4. URL updates
5. Router activates matching route
6. New component renders in <router-outlet>
```

`routerLink` can be used on any clickable html tag.

**Why NOT use href ?**  
Browser performs full page reload, Angular app restarts, State is lost

---
### Active Link Styling
```ts
<a routerLink="/about" routerLinkActive="active"> About </a>
```
Applies active CSS class when route matches

---

### <center> - Programmatic Navigation -

Use programmatic navigation when:  
Navigation depends on logic, 
Happens after something (login, submit, API success)

Injecting the Router :-
```ts
import { Router } from '@angular/router';

constructor(private router: Router) {}
```

Navigating using Router :-
```ts
this.router.navigate(['/home']);
// OR
this.router.navigateByUrl('/home');
```
---

### <center> - Route Parameters -
A Route Parameter is a dynamic value in the URL that Angular captures and makes available to the component

```ts
{ path: 'user/:id', component: UserComponent }
```
These URLs ✅ match:  
/user/1  
/user/99  
/user/abc  

Angular provides a special service called:  
✅ ActivatedRoute  
This service gives information about the current route.

---
Step 1: Inject ActivatedRoute
```ts
import { ActivatedRoute } from '@angular/router';

constructor(private route: ActivatedRoute) {}
```
Step 2: Read the parameter
```ts
ngOnInit() {
  const id = this.route.snapshot.paramMap.get('id'); 
  //paramMap.get() returns STRING
  
  console.log(id);
}
```


---
### Steps :-
1. Go to `app.routes.ts`
    ```ts
    import { Routes } from '@angular/router';
    import { About } from './about/about';
    import { Login } from './login/login';
    import { Contact } from './contact/contact';

    export const routes: Routes = [
      {path:'about', component:About}, 
      {path:'login', component:Login},
      {path:'contact', component:Contact}
    ];
    ```
3. Go to `app.ts` and  
`imports: [RouterOutlet, RouterLink],`

4. Go to `app.html`
    ```html
    <ul>
        <li>
            <a routerLink="/login">Login</a>
        </li>
        <li>
            <a routerLink="/about">About</a>
        </li>
        <li>
            <a routerLink="/contact">Contact</a>
        </li>
    </ul>

    <router-outlet/> //Where to attach
    ```
    ![alt text](image-20.png)


---