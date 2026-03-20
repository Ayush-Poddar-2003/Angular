# DATA BINDING
Data Binding in Angular connects your component (TypeScript logic) with the template (HTML view).  
It allows data to flow between them so the UI updates automatically.

- **One way (.ts -> .html)** :  
Interpolation, Property Binding, Event Binding
- **Two way (.ts <-> .html)** :  
ngModels directives

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

---

### 2.   Property Binding
Sending data from your component (TypeScript file) to the HTML element property.

`[elementProperty]="value"`

```ts
export class AppComponent {
  imageUrl = "https://picsum.photos/200";
}
```
```html
<img [src]="imageUrl">
```

### 3. Event Binding

```ts
showMessage(){
  alert("Hello")
}
```
```html
<button (click)="showMessage()"> Click </button>

<select (change)="showMessage()">
    <option value="Pune">Pune</option>
    <option value="Nagpur">Nagpur</option>
    <option value="Mumbai">Mumbai</option>
    <option value="Delhi">Delhi</option>
</select>
```

---

# <center> 2 Way Binding

> Step 1 : Import `FormsModule` in .ts file where we want data

> Step 2 : Use `[(ngModel)]="Variable"` where we want to store from .html

```html
<input type="text" [(ngModel)]="firstName">
<!-- input text will be addign to firstName -->

<select [(ngModel)]="City">
  <option value="Pune">Pune</option>
  <option value="Nagpur">Nagpur</option>
  <option value="Mumbai">Mumbai</option>
  <option value="Delhi">Delhi</option>
</select>
```
