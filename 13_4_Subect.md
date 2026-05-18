# Subject ?

A Subject is both:  
👉 an Observable ✅ (you can subscribe)  
👉 and an Observer ✅ (you can send data)

```
Subject = WhatsApp group
subscribe() = join group
next() = send message
```

```js
import { Subject } from 'rxjs';

//group created
const subject$ = new Subject();

//Person 1 joined
subject$.subscribe(val => console.log('User 1:', val));
subject$.subscribe(val => console.log('User 2:', val));

//Send to all subscriber
subject$.next('First');
subject$.next('Second');

//Output
// User 1: First
// User 2: First
// User 1: Second
// User 2: Second
```

Another Example :-
```ts
const subject$ = new Subject();

//sent before anyone joined
subject$.next('A');  

// joins NOW
subject$.subscribe(val => console.log(val)); 
subject$.next('B');

// Output
// B
```

You control when to emit, using next(), unlike of() which emit automatically

---
## BehaviorSubject
A BehaviorSubject is a Subject that:  
✅ stores the latest value  
✅ gives it to new subscribers

Subject → no memory ❌  
BehaviorSubject → remembers last value ✅

> BehaviorSubject requires an initial value

```ts
const s = new BehaviorSubject(0);
const s = new BehaviorSubject(10);
s.subscribe(console.log); //10
```
But
```ts
const s = new Subject();
const s =.next(10);
s.subscribe(console.log); //empty
```