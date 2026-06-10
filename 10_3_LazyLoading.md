## <center> -LAZY LOADING-
Without lazy loading, When app starts:  
Angular loads EVERYTHING
(all modules, all components)


```ts
@NgModule({
 declarations:[
   UserListComponent,
   UserDetailComponent
 ]
})
export class UserModule {}
```
```ts
// app.module.ts
imports:[
    UserModule //Module is group of similar components
]
```
---

Suppose your app has:
```
AppModule
│
├── DashboardModule
├── UserModule
├── AdminModule
└── ReportModule
```
And AppModule imports all of them:
```ts
@NgModule({
  imports: [
    DashboardModule,
    UserModule,
    AdminModule,
    ReportModule
  ]
})
export class AppModule {}
// User waits for everything, Even if he never opens:
```

### Lazy Loading Idea
For eg  
Don't load AdminModule now.  
Load it only when someone visits /admin.

```ts
const routes = [
  {
    path: 'admin',
    loadChildren: () =>
      import('./admin/admin.module') //go to file admin.module.ts
        .then(m => m.AdminModule) //search and import export class AdminModule {}
  }
];
```

> Lazy Loading = Loading Angular code later