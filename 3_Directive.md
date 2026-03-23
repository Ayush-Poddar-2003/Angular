# Directive

A Class that adds additional behavior to elements in your applications.    
A feature that gives more power to DOM Elements.

| Type                 | Purpose                     | Example              |
| -------------------- | --------------------------- | -------------------- |
| Component Directive  | Directive with template     | `@Component`         |
| Structural Directive | Changes DOM structure       | `*ngIf`, `*ngFor`    |
| Attribute Directive  | Changes appearance/behavior | `ngClass`, `ngStyle` |


---
### <center> *ngIf
ngIf is used to show or hide something in HTML based on a condition.
> Step 1 : Import `CommonModule` or `NgIf` directly in imports section of .ts
 
```ts
dataLoaded = true;
```
```html
<p *ngIf="dataLoaded; else loadingBlock">Oh yess Data Loaded!</p>

<ng-template #loadingBlock>
  <p>Loading...</p>
</ng-template>
```

The element is not just hidden with CSS.
It is removed from the DOM.

So:  
❌ It doesn’t take space
❌ It’s not clickable
❌ It’s not in the code
❌ It doesn’t exist on the page at all  
It’s like it was never written.

---
### <center> *ngFor
ngFor is used to loop through a list (array) and show items one-by-one in HTML.

```ts
names = ["Ayush", "Raj", "Kunal"];
```

```html
<p *ngFor="let n of names">{{ n }}</p>
<!-- For each value inside names, create one copy of the HTML used with ngFor -->
```
![alt text](image-32.png)

It creates or destroys DOM elements for each item in the list.

**NOTE :-**  
*ngFor gives you extra info for every loop item, called **context variables**.  
One of these is **index** → the position number of the current item (starts at 0).  

```ts
*ngFor="let name of names; let i = index"
```
`let i = index`=> Create a local variable called i and assign the current item’s index to it.

Other context variables: first, last, even, odd, count.
- isFirst gets true only for the first item
- isLast gets true only for the last item
- total = total items
- isEven = index is even
- isOdd = index is odd

```ts
names = ["Ayush", "Raj", "Kunal", "Meera"];
```

```html
<div *ngFor="let name of names; let i = index;
      let isFirst = first;
      let isLast = last;
      let isEven = even;
      let isOdd = odd;
      let total = count">

  {{ i }} - {{ name }}
  | first: {{ isFirst }}
  | last: {{ isLast }}
  | even: {{ isEven }}
  | odd: {{ isOdd }}
  | count: {{ total }}

</div>
```

![alt text](image-33.png)

---
### <center>*ngSwitch
A Structural Directive

```html
<div [ngSwitch]="color">
    <h1 *ngSwitchCase="'red'" style="background-color: red;">Red</h1>
    <h1 *ngSwitchCase="'yellow'" style="background-color: rgb(251, 255, 0);">Yellow</h1>
</div>
```
```ts
export class App {
  color = "yellow"
}
```
![alt text](image-19.png)

---
### <center> *ngClass
ngClass is used to add or remove CSS classes dynamically based on: conditions, values, API data, loop index etc.

`[ngClass]="{ 'CSS_CLASS_NAME': CONDITION }"`

```ts
isActive = true;
```

```html
<p [ngClass]="{ 'highlight': isActive }">Hello Ayush</p>
```

```css
.highlight { color: #e11d48; font-weight: 600; }
```
---
#### ngClass with MULTIPLE CLASSE :-
```html
<span [ngClass]="{
  'active-user': userStatus === 'active',
  'pending-user': userStatus === 'pending',
  'blocked-user': userStatus === 'blocked'
}">   {{ userStatus }}  </span>
```
---
### ngClass with ARRAY :-
Use it when:
You want to apply multiple classes directly.
```html
<div [ngClass]="['card', isBig ? 'big' : 'small']">
  Card Example
</div>
```
```css
.card { padding: 8px; border: 1px solid #ccc; }
.big { font-size: 24px; }
.small { font-size: 14px; }
```