# INTERPOLATION

![alt text](image.png)

```ts
//app.ts

import { Component, signal } from '@angular/core';
import { RouterOutlet } from '@angular/router';

@Component({
  selector: 'app-root',
  imports: [RouterOutlet],
  templateUrl: './app.html',
  styleUrl: './app.css'
})
export class App {
  name="Ayush Poddar"
}
```
```ts
// app.html

<H1>INTERPOLATION</H1>
{{name}}
```