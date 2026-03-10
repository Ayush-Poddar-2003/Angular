# Effect
effect() tracks signals used inside it and re-executes when any of those signals change.


```ts
// App.ts
export class App {
  count = signal(1);

  constructor(){
    effect( ()=>{
      console.log("Count Changed ",this.count());
    })

    this.count.set(2);
    this.count.set(3);
    this.count.set(4);
  }
}
```


