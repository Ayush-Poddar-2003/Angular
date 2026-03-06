# Function -
```ts
// app.ts
export class App {
  handleClickEvent(){
    alert("Hey Babe");
  }
}
```

```html
<!-- app.html -->
<button (click)="handleClickEvent()"> Click Me </button>
```