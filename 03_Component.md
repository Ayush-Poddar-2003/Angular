# Component

A self‑contained block of UI + logic that controls a specific part of the screen.  

    ng g c header

Angular creates a folder: `src/app/header/`

Inside it, 4 files:  
```
header.component.ts     ← LOGIC (brain)
header.component.html   ← UI (face)
header.component.css    ← STYLE (looks)
header.component.spec.ts← testing (ignore for now)
```

---
### How Angular knows something is a Component ?
Angular doesn’t guess.  
You explicitly tell Angular using a Decorator:
`@Component`

```ts
// header.component.ts
@Component({
  selector: 'app-header',
  standalone: true,
  imports: [],
  templateUrl: './header.component.html',
  styleUrls: ['./header.component.css']
})

export class HeaderComponent {
  title = 'My Header';

  logout() {
    console.log('Logged out');
  }
}
```

1. Selector  
The selector tells Angular how to place this component in HTML.  
`selector: 'app-header'`  
    ```html
    <!-- app.component.html -->
    <app-header></app-header>
    ```