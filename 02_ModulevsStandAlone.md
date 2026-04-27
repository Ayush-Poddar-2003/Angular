## <center>Module-based vs Standalone

#### 1. STANDALONE :-
![alt text](image-37.png)

❌ No app.module.ts  
✅ Has app.config.ts

---
#### 2. MODULE BASED :-
![alt text](image-38.png)


---
Earlier Angular versions, By default created a Module‑based project Now Stand-Alone.


Earlier we had `app.module.ts`

Let's say we want to use `*ngIf, *ngFor, ngModel`  
In Module‑Based Angular, You must:

    Open app.module.ts
    Import required modules, Add them to imports: []

```ts
//app.module.ts
@NgModule({
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

# <CENTER> Module
An Angular Module is:  
A container that groups related components, directives, pipes, and services.

If EVERYTHING lives in one place:  
❌ files become messy
❌ hard to maintain
❌ slow loading

---

### AppModule ?
- Students = Components
- Subjects = Angular features (Forms, HTTP, routing)
- College administration = AppModule

one main file that tells me everything

#### What Does AppModule Contain?
1. Declarations Box: “Which components are part of my app?”
2. Imports Box: Which powers does my app have?
3. Bootstrap Box: Which component should i show first
4. Provider Box: Which services are available app‑wide?
```ts
//app.module.ts

@NgModule({ //decorator
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

> AppModule = permission list for the whole app  
> Standalone component = permission list for itself