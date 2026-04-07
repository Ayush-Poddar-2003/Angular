## TWO‑WAY DATA BINDING

- When the user types in the input → the .ts variable updates ✅
- When the variable changes in .ts → the input updates ✅

---

### How Angular does this ?

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
### Imports ?

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
