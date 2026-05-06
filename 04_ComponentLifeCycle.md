# Component Life Cycle
The sequence of stages a component goes through from creation → updates → destruction.

A component is like an app screen:

1. Created (loaded)
2. Data comes in
3. UI updates multiple times
4. Finally removed

Angular does NOT run everything at once.  
It runs your component in phases, and lifecycle hooks let you:
> “inject your logic at the right time”

---
### Lifecycle Hooks ?
Special methods that Angular automatically calls at different stages of a component’s life.  
You don’t call them → Angular calls them for you.


```
ngOnChanges()
ngOnInit()
ngDoCheck()
ngAfterContentInit()
ngAfterContentChecked()
ngAfterViewInit()
ngAfterViewChecked()
ngOnDestroy()
```
---

## ngOnInit
Runs once, after the component is initialized and ready.  
Safe place for: API calls, Initial data setup, Subscriptions

## ngOnChanges
ngOnChanges() runs whenever data received via @Input() changes.  
Runs before ngOnInit() (first time)  
Runs every time input value changes

## ngDoCheck (Custom Change Detection)
Angular automatically checks:  
Has data changed?
Should UI update?  
Every time it checks → ngDoCheck() runs, multiple times, if consoled, multi logs

## <center> ngAfterViewInit
ngAfterViewInit() runs after the component’s view (HTML/UI) is fully loaded.  
This means, After this hook:  
✅ UI is fully rendered  
✅ DOM elements can be accessed safely

UseCases :-  
- TypeScript needs HTML elements
- using @ViewChild
- DOM interaction needed

```html
<input #myInput>
```

```ts
@ViewChild('myInput') input: any;

ngAfterViewInit() {
  this.input.nativeElement.focus();
}
```
What's ongoing
1. Angular loads HTML:
2. @ViewChild gets that input element
3. When UI fully appears `ngAfterViewInit()` runs
4. `this.input.nativeElement.focus();` executes

Put cursor inside input box automatically.

---

## <center> ngOnDestroy
Runs right before a component gets removed from the screen.

