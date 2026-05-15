# Retry
In real-world apps, APIs fail often:  
🌐 Network instability  
🖥️ Server temporarily down  
⏳ Timeout issues  
📶 Slow connections

---

Without retry:  
Request fails → App shows error immediately

With retry:  
Request fails → Retry automatically → May succeed

---

Retry means automatically re-sending a failed request

```ts
import { retry } from 'rxjs/operators';

this.http.get('/users').pipe(
  retry(2)
).subscribe(data => {
  console.log(data);
});
```

First request + 2 retries:   
Total attempts = 3

Retry works ONLY on errors   
Retry re-sends entire request

---
## Using retryWhen
```ts
import { retryWhen, delay, take } from 'rxjs/operators';

this.http.get('/users').pipe(
  retryWhen(errors =>
    errors.pipe(
      delay(1000), // wait 1 sec before retry
      take(3)      // retry 3 times
    )
  )
).subscribe();
```