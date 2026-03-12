# Services 
A service is a class used to store reusable logic or data that multiple components can use.

Example responsibilities of a service:
- calling APIs
- authentication
- sharing data between components

![alt text](image-26.png)
---

## Why Angular Uses Services ?

Imagine you have 3 components:  
HomeComponent, DashboardComponent, ProfileComponent  

All three need user data from an API.
```
HomeComponent → API
DashboardComponent → API
ProfileComponent → API
```
You will repeat the same code.  
Instead you create one service:  

```
UserService → API 

HomeComponent → UserService
DashboardComponent → UserService
ProfileComponent → UserService
```

## What a Service Looks Like ?
A service is just a TypeScript class.
```ts
export class UserService {
  getUsers(){
    return ["John", "Sara", "Mike"]
  }
}
```

Creating a Service: 
`ng g s serviceFolder/serviceName`

if `ng generate service user`
Angular will create:
```
user.service.ts
user.service.spec.ts
```
---
```ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})

export class UserService {

  getUsers() {
    return ["John", "Sara", "Alex"];
  }

}
```
### What is @Injectable?  
Tells Angular "This class can be injected into other classes."

---
# Using a Service in a Component

```ts
// UserService
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class UserService {

  getUsers() {
    return ["John", "Sara", "Mike"];
  }

}
```
```ts
// home.ts
import { Component } from '@angular/core';
import { UserService } from './user.service'; //importing service

@Component({
  selector: 'app-home',
  template: `<p>{{ users }}</p>`
})

export class HomeComponent {

  users: string[] = [];
 
  // give me an instance of UserService & store it in variable → us
  constructor(private us: UserService) 
  {
    this.users = this.us.getUsers();
    //this.us => service object, hence used to call
  }

}
```

```html
<li *ngFor="let user of users">
  {{ user }}
</li>
```