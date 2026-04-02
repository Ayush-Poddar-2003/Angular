# DATA BINDING
Data Binding in Angular connects the Component class (TypeScript) with the Template (HTML) so the UI stays in sync with data.   
It allows data to flow between them so the UI updates automatically.

- **One way binding** :
  - .ts → .html : Interpolation, Property Binding [ ]
  - .html → .ts : Event Binding ( )

- **Two way (.ts <-> .html)** :  
  - Combines { `Property[ ] and Event Binding( )` }
  - `[(ngModel)]`

---

### 1. INTERPOLATION

> Showing a TypeScript variable value inside HTML  

`{{ expression }}` , The expression can include:  
variables, calculations, method calls, string operations
```ts
//app.ts
export class App 
{
  name="Ayush Poddar" 
  
  getGreeting(){
    return "Welcome to Angular";
  }
}
```
```ts
// app.html
{{name}}

<h2>{{ getGreeting() }}</h2>
```
![alt text](image-31.png)
---

### 2.   Property Binding

`[elementProperty]="value"`,  
value is a component property (TypeScript variable)

```ts
export class AppComponent {
  imageUrl = "https://picsum.photos/200"; //variable
}
```
```html
<img [src]="imageUrl">
```

---

### 3. Event Binding

.html -> .ts

```html
<!-- app.html -->
<button (click)="handleEvent($event)" class="btn" name="btname" > Click Event </button>
```
```ts
// app.ts
export class App 
{
  handleEvent(event:any) //any as datatype
  {
    console.log("Function Called: ", event);
    console.log("Class Name: ", event.target.className);
    console.log("Name: ", event.target.name);
  }
}
```

![alt text](image-9.png)

---

### Mouse Event -
```ts
export class App {
  handleEvent(event:MouseEvent){ //MouseEvent
    console.log("Function Called: ", event);
    console.log("Event Type: ", event.type);
    console.log("Event Target: ", event.target);
    console.log("Class Name: ", (event.target as Element).className);
  }
}
```

![alt text](image-10.png)

---
```html
<div (mouseenter)="handleEvent($event)"
style="background-color: green; width: 100px; height: 100px;">
</div>
<div (mouseleave)="handleEvent($event)"
style="background-color: rgb(19, 0, 128); width: 100px; height: 100px;">
</div>
```
![alt text](image-12.png)

---

### Input

```html
<input type="text"
(input)="handleEvent($event)">
```
```ts
export class App 
{
  handleEvent(event:Event){
    console.log("Function Called: ", event);
    console.log("Class Name: ", (event.target as HTMLInputElement).value);
  }
}
```
![alt text](image-13.png)