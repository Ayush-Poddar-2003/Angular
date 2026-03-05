
```ts
// app.ts
import { Component, signal } from '@angular/core';
import { RouterOutlet } from '@angular/router';

@Component({
  selector: 'app-root',
  imports: []
})
export class App {
  handleClickEvent(){
    alert("Hey Babe");
  }
}
```

```html
<!-- app.html -->
<h1>YO</h1>

<button (click)="handleClickEvent()">Click Me</button>
```