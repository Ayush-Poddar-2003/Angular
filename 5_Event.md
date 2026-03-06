# Events

```html

<!-- app.html -->
<button (click)="handleEvent($event)">Click Event</button>

```
```ts
export class AppComponent{
    handleEvent(event:any){
        console.log("Function Called", event);
    }
}
```