## <center>Project Types

#### 1. STANDALONE :-
![alt text](image-37.png)

❌ No app.module.ts  
✅ Has app.config.ts

---
#### 2. MODULE BASED :-
![alt text](image-43.png)

---

# <CENTER> Module ?

When Angular (older style) starts, the first thing it looks for is `app.module.ts`  

A module is the main configuration file that tells Angular how your app is structured


---

#### What Does Module Contain?
```ts
@NgModule({
  declarations: [],
  imports: [],
  providers: [],
  bootstrap: []
})
export class AppModule {}
```
1. @NgModule:   
This file is a module and here is its configuration
2. Declarations Box:  
List of components that belong to this module
3. Imports Box:  
List of other modules this module depends on
4. Provider Box: Which services are available app‑wide?
5. Bootstrap Box:  
Defines the starting component of the application






Earlier Angular versions, By default created a Module‑based project Now Stand-Alone.


Earlier we had `app.module.ts`

Let's say we want to use `*ngIf, *ngFor, ngModel`  
In Module‑Based Angular, You must:

    Open app.module.ts
    Import required modules, Add them to imports: []

```ts
//app.module.ts

@NgModule({ //first decorator @NgModule
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    FormsModule   // 👈 needed for ngModel
  ],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

```ts
// demo.component.ts
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html'
})
export class AppComponent {
  name = '';
}
```
```html
<!-- demo.component.html -->
<input [(ngModel)]="name" />
<p *ngIf="name">Hello {{ name }}</p>
```
> Works only because: FormsModule was added in app.module.ts

---
In Standalone
```ts
// app.component.ts
@Component({
  selector: 'app-root',
  standalone: true, //Important line
  imports: [        //Imported directly
    CommonModule,
    FormsModule //added in exact file
  ],
  templateUrl: './app.component.html'
})
export class AppComponent {
  name = '';
}
```
---
