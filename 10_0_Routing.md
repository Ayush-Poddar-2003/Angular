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

✅ Angular Router is constantly watching the URL   
✅ It parses the url into path, params etc                                         
✅ Matches routes from app.routes.ts  
✅ Checks Guards  
✅ Component lifecycle, Old component destroyed, New created  
✅ Angular inserts component into ``<app-router>``  
✅ Change detection runs  
✅ UI updates automatically

>   Angular routing works entirely on the client side after initial load



---
## <center> Core Pieces
### (1) Routes (Configuration)
Defines mapping in app.routes.ts :-


### (2) Router Outlet (Display Area)
👉 Where content shows  
When route matches:
Angular creates component instance &
Inserts it inside `<router-outlet>...</router-outlet>`

---

```html
<app-navbar></app-navbar>
<router-outlet></router-outlet>
<app-footer></app-footer>
```
Now AppComponent says:  
Navbar always visible.  
Middle section changes according to route.  
Footer always visible.  

---

## <CENTER> Route Configuration

An array of objects that defines:  
URL path → What should happen

```ts
const routes: Routes = [
  { path: 'home', component: HomeComponent },
  { path: 'login', component: LoginComponent },
  { path: 'about', component: AboutComponent }
];
```
Empty Path :-
`{ path: '', component: HomeComponent }`  
Empty path ' ' represents the root URL (/)


### REDIRECTS -

```ts
{ path: '', redirectTo: 'home', pathMatch: 'full' }
```
Do NOT render component → Just change URL 

**pathMatch** ?  
Angular can match routes in two ways:  
1. `prefix`: default behaviour i.e. Match starting part of URL  
`{ path: '', redirectTo: 'home' }`  
Angular interprets ' ' or / as a prefix of every URL,   
Result:
👉 Infinite redirect loop as every url starts with `/`
2. `full`   
`{ path: '', redirectTo: 'home', pathMatch: 'full' }`: Only redirect when the entire URL is exact `\`

> Always use `pathMatch: 'full'` for empty routes
---

#### WILDCARD ROUTE

```ts
{ path: '**', component: PageNotFoundComponent }
```  
Match ANY URL that was not matched before, Many routes don’t exist.  
Without wildcard:
❌ App breaks / blank screen  
Wildcard must ALWAYS be last



### <CENTER> ROUTE ORDER

1. Angular Checks first route
2. If match → stops
3. Does NOT check further

```ts
//correct order
const routes = [
  { path: '', redirectTo: 'auth', pathMatch: 'full' },
  { path: 'auth', component: LoginComponent },
  { path: '**', component: NotFoundComponent }
];
```


## <center> Nested Routing
#### 1. Absolute
`<a routerLink="/home/profile"> Go </a>`  

`this.router.navigate(['/home/profile']);`

#### 2. Relative
Assume you already on `/home`  

```html
<a routerLink="profile">Go</a>
```
```ts
this.router.navigate(['profile'], {
  relativeTo: this.route
});
```

Goes to `/home/profile`

#### 3. Children
Routes inside another route
```ts
{
  path: 'home',
  component: HomeComponent,
  children: [
    { path: 'profile', component: ProfileComponent }
  ]
}
```
```
/profile ❌ does NOT exist, child
/home/profile ✅ does exist
```
Good practice to make a default child route
```ts
{
  path: 'home',
  component: HomeComponent,
  children: [
    { path:'', redirectTo: 'profile', pathMatch: 'full' },
    { path:'profile', component: ProfileComponent }
  ]
}
```
Now if user goes to:
`/home`  
1. Angular Loads parent
2. Matches ' '
3. Redirects to /home/profile

---
