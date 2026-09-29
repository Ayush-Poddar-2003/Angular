# Form

### 1️⃣ TEMPLATE-DRIVEN FORMS
👉 Simple  
👉 Logic mostly in HTML  
👉 Uses ngModel  

### 2️⃣ REACTIVE FORMS
👉 More control  
👉 Logic in TypeScript  
👉 Uses FormGroup, FormControl

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
<form #var="ngForm" (ngSubmit)="signUp(var.value)">
  <input type="text" ngModel name="name">
  <input type="password" ngModel name="password">
  <input type="text" ngModel name="email">
  <button>Sign Up</button>
</form>
```
Angular automatically builds this object for you:

```json
var.value = {
  name: "whatever user typed",
  password: "whatever user typed",
  email: "whatever user typed"
}
//then
(ngSubmit)="signUp(var.value)"
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



