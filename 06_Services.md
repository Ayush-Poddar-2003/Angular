# Services 
A service is a class used to store reusable logic or data that multiple components can use.

- calling APIs, authentication, sharing data between components



Imagine you have 3 components:  
HomeComponent, DashboardComponent, ProfileComponent    
All three need **UserData** from an API.
```
HomeComponent → API
DashboardComponent → API
ProfileComponent → API
```
You will repeat the same code with all component.  
Instead you create one service:  

```
UserService → API 

HomeComponent → UserService
DashboardComponent → UserService
ProfileComponent → UserService
```
![alt text](image-26.png)





# Dependency Injection ?
DI is a pattern where Angular creates & supplies(injects) the dependencies(services) your class needs  
— you just declare them in the constructor.


----
### Creating a Service:   
`ng g s serviceFolder/serviceName`


```ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})

export class UserService {

  //what to return
  getUsers() {
    return ["John", "Sara", "Alex"];
  }

}
```
### @Injectable?  
Tells Angular "This class can be injected into other classes."

---
### Using a Service in a Component

```ts
// user.service.ts
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
export class HomeComponent {

  users: string[] = [];
 
  // give me an instance of UserService & store it in variable → us
  constructor(private us: UserService) 
  {
    this.users = this.us.getUsers();
  }
}
```
---

```ts
// Old way
constructor(private userService: UserService) {}

// New way
const userService = inject(UserService);
```