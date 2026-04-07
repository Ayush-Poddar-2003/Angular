# Services 
A class to store reusable logic/data that multiple components can use.


Imagine you have 3 components:  
- HomeComponent, DashboardComponent, ProfileComponent    

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
`@Injectable` :  
Tells Angular "This class can be injected into other classes."

`providedIn: 'root'` :  
Angular will create 1 single instance of this service & share it across the whole app, 
So if :  
- Component A updates data in the service 
- Component B sees the updated data

---
### Dependency Injection ?
DI is a pattern where Angular creates service & supplies(injects) the dependencies(services) to all your classes.  
We just declare them in the constructor.

---

```ts
// user.service.ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class UserService {

  username = 'Ayush';

  getUsername() {
    return this.username;
  }
}
```
```ts
// Component.ts
import { Component } from '@angular/core';
import { UserService } from './user.service';

@Component({
  selector: 'app-home',
  templateUrl: './home.component.html'
})
export class HomeComponent {

  constructor(private userService: UserService) {}

  ngOnInit() {
    console.log(this.userService.getUsername());
  }
}
```
---

```ts
constructor(private userService: UserService) {}

// Alternate way
const userService = inject(UserService);
```