# Async Pipe?
Used in HTML to automatically subscribe to an Observable.

Observable → async pipe → value shown in HTML

No manual .subscribe() needed ✅

Problem Without Async Pipe :-  
manual subscribe, 
manual data assignment, 
must unsubscribe in some cases

For eg
```ts
data$ = this.http.get<any[]>('/api');
```
```html
<div *ngFor="let item of data$ | async">
  {{ item.name }}
</div>
```

For eg
```ts
data$ = of(1, 2, 3);
```
```html
{{ data$ | async }} //3
```
>  Async pipe always shows the latest emitted value

If you WANT to show all values,
You must use array