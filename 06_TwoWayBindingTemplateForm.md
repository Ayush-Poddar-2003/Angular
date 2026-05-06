## 2‑WAY DATA BINDING / Template Driven Form

- When the user types in the input → the .ts variable updates ✅
- When the variable changes in .ts → the input updates ✅

---

### How  ?

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
### Necessities ?

### 1. For Standalone :-

1. ngModel is NOT built‑in, we need to import `FormsModule`
    ```ts
    import { FormsModule } from '@angular/forms';

    @Component({
      standalone: true,
      imports: [FormsModule]
    })
    ```
2. You must add name attribute:  
    ```html
    <input [(ngModel)]="firstName" name="firstName">
    ```

### Module Based :-

1. Open app.module.ts → add FormsModule
    ```ts
    //app.module.ts
    import { FormsModule } from '@angular/forms';

    @NgModule({
      declarations: [SellerAuth],
      imports: [FormsModule],
    })
    export class AppModule {}
    ```
---

Now from just databinding => Actual form control

Angular gives:  
- ngForm → creates a form object
- ngSubmit → handles submit

---
### <center> 1️⃣ ngForm (Form Object)

```html
<form #myForm="ngForm">
```

`#myForm` is variable,  # is used to create a local variable inside HTML.  
Angular already has something called `ngForm`
(it represents the whole form)

>Take Angular’s form object (ngForm) & store it in my variable myForm

Now Angular tracks:
All inputs, their values, form state

`console.log(myForm.value)` => We can access everyinput

---
### <center> 2️⃣ ngSubmit (Submit handler)
```html
<form (ngSubmit)="onSubmit(myForm)">
```

( ) → event binding  
ngSubmit → submit event  
onSubmit → your function  
myForm → your variable


👉When user clicks submit:  
Angular prevents reload, Calls your function, Sends full form data

For e.g.  
```html
<form #sellerSignup="ngForm" (ngSubmit)="signUp(sellerSignup.value)">
  <input type="text" ngModel name="name">
  <input type="password" ngModel name="password">
  <input type="text" ngModel name="email">
  <button>Sign Up</button>
</form>
```
Angular automatically builds this object for you:

```ts
sellerSignup.value = {
  name: "whatever user typed",
  password: "whatever user typed",
  email: "whatever user typed"
}
//then
(ngSubmit)="signUp(sellerSignup.value)"
//You directly pass all form data as an object
```
---
## <center> VALIDATIONS

```html
<input type="email" required>
<input type="password" minlength="6">
```
How do we know based on input type, is the given input even valid ?

```html
<input name="name"
  [(ngModel)]="name"
  #nameRef="ngModel"
  required
>
<!-- Create variable nameRef, which holds this input’s state
Now we can check using -->

nameRef.valid
nameRef.invalid
nameRef.touched
```

#### Show error message :-
```html
<div *ngIf="nameRef.invalid && nameRef.touched">
  Name is required
</div>
```

#### Disable submit if form invalid :-
```html
<button type="submit" [disabled]="myForm.invalid">
  Submit
</button>
```

