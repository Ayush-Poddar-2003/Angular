# Creating Observables
There are 4 main ways
1. new Observable( )   (manual)
2. of( )               (most common)
3. from( )
4. interval( )

## 1. Manual : new Observable( )
Rarely used, Only when you want custom control
```ts
const obs$ = new Observable((observer) => {
  observer.next('A');
  observer.complete();
});
```

## <CENTER> 2. of( )

of() is used to create an Observable that emits given values

Instead of manually writing:
```
observer.next(1);
observer.next(2);
observer.next(3);
```
You can simply write: `of(1, 2, 3)`

For eg
```ts
import { of } from 'rxjs';

const obs$ = of(1, 2, 3);
```
```ts
obs$.subscribe((data) => {
  next: (val) => console.log(val),
  complete: () => console.log('Done')
});

// 1 2 3 Done, in seprate lines
```
Another example :-  
```ts
of("A", "B", "C").subscribe(console.log);
// A B C
```
---

## <center> 3. from( )
Convert existing data (array, promise, string) into observable

eg, using array

```ts
import { from } from 'rxjs';

const obs$ = from([10, 20, 30]);
```
eg, using promise
```ts
const promise = fetch('ApI/users');

const obs$ = from(promise);
```

---
## <center> 4. Interval( )
Emits values repeatedly after a fixed time
```ts
import { interval } from 'rxjs';

const obs$ = interval(1000);
```
```ts
obs$.subscribe(val => console.log(val));
```
    0   (after 1 sec)
    1   (after 2 sec)
    2   (after 3 sec)
    3   (after 4 sec)

`interval()` never stops by itself, You must **unsubscribe**

---
Different Cases :-  
`of(1, 2, 3)`  
1  
2  
3

`of([1, 2, 3])` [1,2,3]  
`from([1, 2, 3])`  
1  
2  
3

---

