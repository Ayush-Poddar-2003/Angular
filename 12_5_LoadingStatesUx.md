## Loading States & UX

When you call an API:  
👉 It takes time (1–3 seconds sometimes)

Without handling this:  
User clicks button -> 
NOTHING happens on screen ->
User thinks app is broken

---
### Basic Loading State Concept :-
Loading = “API request is in progress”

We use a boolean flag :-
```ts
isLoading = false;
users: any[] = [];

loadUsers() {
  this.isLoading = true; // start loading

  this.http.get('/users').subscribe({
    next: (data: any) => {
      this.users = data;
      this.isLoading = false; // stop loading
    },
    error: () => {
      this.isLoading = false; // stop loading even if error
    }
  });
}
```

### Show Loader in UI
```html
<button (click)="loadUsers()">Load Users</button>

<div *ngIf="isLoading">
  Loading...
</div>

<div *ngIf="!isLoading">
  <div *ngFor="let user of users">
    {{ user.name }}
  </div>
</div>
```

---
> Disable Button During Request
```html
<button (click)="loadUsers()" [disabled]="isLoading">
  Load Users
</button>
```
Prevent multiple clicks, 
Avoid duplicate API calls

---
### Use RxJS finalize