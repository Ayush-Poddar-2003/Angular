# Memory Leak?
A memory leak happens when something keeps running in memory even when you don’t need it

Imagine:  
User opens a page,
Component loads,
Observable starts

👉 Then user navigates away…  
❌ But Observable is still running in background  
➡️ That is a memory leak

For eg:-
```ts
ngOnInit() {
  interval(1000).subscribe(val => {
    console.log(val);
  });
}
```
What happens?  
Component loads → interval starts  
User navigates away  
Interval is still running in background  

---

## ngOnDestroy
A lifecycle hook that runs when Angular destroys the component

**When does it run** ?  
Navigate to another page, Component removed from DOM, Parent component destroys child etc

```ts
export class HomeComponent implements OnInit, OnDestroy {

  sub!: Subscription;

  ngOnInit() {
    this.sub = interval(1000).subscribe(val => {
      console.log(val);
    });
  }

  ngOnDestroy() {
    this.sub.unsubscribe();
  }
}
```