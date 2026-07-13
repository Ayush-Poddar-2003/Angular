# <center>INTRODUCTION

### ANGULAR ?   
Released in **2010 (AngularJS)** by Google  
Created by **Misko Hevery and Adam Abrons**  
Originally called **AngularJS (Deprecated)**, currently **Angular (2+)**.

> ⚠️ AngularJS and Angular are different frameworks.

- Angular is not just a UI library like React. It is a full‑fledged framework.  
**Library**: You are in charge. Your code calls the library's functions to perform specific tasks.  
**Framework**: The framework is in charge. It provides a skeleton or blueprint, and it calls your code at specific "hooks" to fill in the functionality


---
### ARCHITECTURE ?

**AngularJS (1.x) : MVC**
1. **MODEL** : Data + Business Logic, what data we have, how we handle it.
2. **VIEW**  : UI, The screen user sees.
3. **CONTROLLER**  : Middleman, connects View ↔ Model.

**Angular (2+)** :  
It uses **Components + Services + Dependency Injection**.


### Angular Versions
- AngularJS → Version 1.x (deprecated)
- Angular → Version 2+ (complete rewrite)
- Angular 16+ → Includes Signals (modern)


---
### INSTALLATION ?

Go to https://angular.dev/installation  
Install Angular CLI (@angular/cli) once using  

    npm i -g @angular/cli  //-g means global

    ng version //to verify

---
### For Every New Project:-
Go to that folder  
`ng new <ProjectName>`  
`cd <ProjectName>`  
`ng serve`  To run server  
It will run on 
 http://localhost:4200/  

TO SEE ALL ng commands `ng help`  

---
## <center>ANGULAR CLI 
> Command Line Interface for Angular.

Tool that helps developers  
Create, build, test, and deploy angular applications.  


**WHY WE NEED IT ?**  
Angular projects have:  
Strict structure, Multiple config files, TypeScript setup, Build configuration  
CLI automates all that.

Without CLI → setup would take 1–2 hours manually.  
With CLI → 1 command.


---

## <center> SPA vs MPA
How MPA works

1. User clicks a link
2. Browser sends a request to the server
3. Server returns a new HTML page
4. Browser reloads the entire page

Each page = separate HTML file  
Full page reload every time

SPA :-  
The browser loads only ONE HTML file,  
URL change = Angular decides which component to show

---


## <center> HOW PROJECT STARTS

### Older style :-
`ng new my-app`
```
src/
│
├── index.html
├── main.ts
│
└── app/
    ├── app.module.ts
    ├── app.component.ts
    ├── app.component.html
    └── app.component.css
```

1. ng serve
2. Browser Opens `index.html`
    ```html
    <body>
        <app-root></app-root>
    </body>
    ```
    But browser doesn't know what that tag app-root is, So it waits.
3. `main.ts` Executes
    ```ts
    platformBrowserDynamic().bootstrapModule(AppModule)
    ```
4. Angular Loads `AppModule`
    ```ts
    @NgModule({
        declarations: [ AppComponent ],
        imports: [ BrowserModule ],
        bootstrap: [ AppComponent ]
    })
    export class AppModule {}
    ```
    4.1) `declarations: [ AppComponent, NavbarComponent, ... ]`  
        Angular, these are the components I know about   
    4.2) `imports: [
  BrowserModule,
  FormsModule,
  HttpClientModule
]`  
Bring external functionality.  
    4.3) `bootstrap: [ AppComponent ]`  
    Start application with AppComponent.

5. Angular Creates AppComponent
    ```ts
    @Component({
        selector:'app-root'
    })
    ```
6. Angular Loads AppComponent HTML

---
### Newer Style :-
```ts
import { bootstrapApplication } from '@angular/platform-browser';
import { provideRouter } from '@angular/router';
import { provideHttpClient } from '@angular/common/http';

import { AppComponent } from './app/app.component';
import { routes } from './app/app.routes';

bootstrapApplication(AppComponent, {
  providers: [
    provideRouter(routes),
    provideHttpClient()
  ]
}).catch(err => console.error(err));
```