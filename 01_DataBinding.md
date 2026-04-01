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

```ts
//to be used on events
showMessage(event: Event) {
  console.log(event);
}
```
```html
<button (click)="showMessage($event)">Click</button>

<select (change)="showMessage()">
    <option value="Pune">Pune</option>
    <option value="Nagpur">Nagpur</option>
    <option value="Mumbai">Mumbai</option>
    <option value="Delhi">Delhi</option>
</select>
```
