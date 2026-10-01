## <center> -LAZY LOADING-
Without lazy loading, When app starts:  
Angular loads EVERYTHING
(all modules, all components)


Suppose your app has:
```
AppModule
│
├── DashboardModule
├── UserModule
├── AdminModule
└── ReportModule
```
And AppModule imports all of them, choas, slowing of app
```ts
@NgModule({
  imports: [
    DashboardModule,
    UserModule,
    AdminModule,
    ReportModule
  ]
})
export class AppModule {}
// User waits for everything, Even if he never opens:
```
---
### Lazy Loading Idea 
Load only when someone visits

```ts
{
  path: 'auth',

  loadChildren: () =>
    import('./Signup-and-Login/user-login.module')
    .then( (m) => m.UserLoginModule ),

  canActivate: [LoginFailedGuard],
},
```

1. loadChildren:, like one of the key of json   
“Angular, don't load this now. Load it when the user needs it.”

2. import('./trace/trace.module')  
It loads that file dynamically and gives you a Promise.

3. .then()  
"When the Promise finishes, do this."

4. (m) => m.TraceModule  
Take the value I receive as m, and return m.ModuleName.

---

    User navigates to /trace
            ↓
    Angular calls loadChildren()
            ↓
    import('./trace/trace.module')
            ↓
    Trace module file gets loaded
            ↓
    .then(...) runs
            ↓
    Take TraceModule from the loaded file
            ↓
    Give TraceModule to Angular Router
            ↓
    Router loads the Trace feature