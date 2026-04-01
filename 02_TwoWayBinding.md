## TWO‑WAY DATA BINDING

Two‑way binding keeps a **component variable (.ts)** and an  
**input element (.html)** in sync automatically.

### What does that mean?
- When the user types in the input → the variable updates ✅
- When the variable changes in .ts → the input updates ✅

This is called **two‑way data binding**.

---

### How Angular does this

Angular provides the directive: `[(ngModel)]`

It combines:
- Property Binding → data from .ts to .html
- Event Binding → data from .html to .ts

So data flows in **both directions**.

---

```html
<input [(ngModel)]="firstName">

<!-- Internally -->
<input
  [ngModel]="firstName"
  (ngModelChange)="firstName = $event"
/>
```
[ngModel] → send value to HTML  
(ngModelChange) → send value back to TS

---
### Why FormsModule ?

ngModel is NOT built‑in, It comes from FormsModule

```ts
// component.ts
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-root',
  standalone: true,
  imports: [FormsModule],
  templateUrl: './app.component.html'
})
export class AppComponent {
    firstName:string = "";
    City:string = "";
}
```
```html
<!-- html, taking user input -->
<input type="text" [(ngModel)]="firstName">

<select [(ngModel)]="City">
  <option value="Pune">Pune</option>
  <option value="Nagpur">Nagpur</option>
  <option value="Mumbai">Mumbai</option>
  <option value="Delhi">Delhi</option>
</select>
```
