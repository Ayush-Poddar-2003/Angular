# COMPONENT 

WHAT ?  
Building blocks, reusable things 

Mostly every components has 4 parts
1. .css
2. .html
3. .spec.ts => For testing
4. .ts => For logics

---
### Generate Component :-
`ng generate component <Name>` OR `ng g c test`  
CLI automatically creates `<Name>` component inside app component:

Exmple:-

    ng generate component login

![ ](image-5.png)

---
### Linking Custom Component & App :-
 

1. Go to login.ts
2. Copy the selector name
![alt text](image-6.png)
3. Use that as a tag in app.html
![alt text](image-7.png)
4. Go to `app.ts`, add import of that component
![alt text](image-8.png)

---

### CREATING COMPONENT FROM SCRATCH -
1. Create a folder with small case start eg`profile`  
2. We must have .ts file, other are non mandatory  
3. 
    ```ts
    import { Component } from "@angular/core";

    @Component({
        selector:'app- profile',
        template:`<h1>Profile Component</h1>`
    })

    export class ProfileComponent{    
    }
    ```
4. 