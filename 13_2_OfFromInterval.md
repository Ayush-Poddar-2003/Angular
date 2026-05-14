## <CENTER> of( )

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

const obs = of(1, 2, 3);
```
```ts
obs.subscribe((data) => {
  console.log(data);
});

// 1 2 3
```
Another example :-  
```ts
of("A", "B", "C").subscribe(console.log);
// A B C
```
---

## <center> from( )
from() = convert existing data (array, promise, string) into observable

👉 of( ) → you give values directly  
👉 from( ) → you give something that already exists

```ts
of([1, 2, 3])

// [1, 2, 3]   // whole array as ONE value
```

```ts
from([1, 2, 3])

// 1
// 2
// 3, each value separately
```

---
## <center> Interval( )
interval() creates an Observable that emits values repeatedly after a fixed time
```ts
import { interval } from 'rxjs';

const obs = interval(1000);
```
```ts
obs.subscribe((data) => {
  console.log(data);
});
```
    0   (after 1 sec)
    1   (after 2 sec)
    2   (after 3 sec)
    3   (after 4 sec)

`interval()` never stops by itself