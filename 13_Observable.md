
> API → subscribe → store in variable → HTML uses it
```ts
data: any[] = [];

ngOnInit() {
  this.http.get<any[]>('api').subscribe(res => {
    this.data = res;
  });
}
```
```html
<div *ngFor="let item of data">
  {{ item.name }}
</div>
```

---
### New way (Observable + async pipe)

> API → directly to HTML, async handles subscribe automatically

```ts
data$ = this.http.get<any[]>('api');
```
```html
<div *ngFor="let item of data$ | async">
  {{ item.name }}
</div>
```

#### What async pipe does ?

👉 It subscribes for you, gives data to HTML, unsubscribes automatically  
So you don’t write .subscribe() manually