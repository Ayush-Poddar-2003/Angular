## <center> ROUTE GUARDS
A guard is a check that runs before navigation happens

**Why we use guards ?**  
To control access based on:  
Login status, 
Permissions, 
Roles, 
Conditions

### <center> - CanActivate Guard -
 
`ng generate guard auth`  

Angular creates: `auth.guard.ts`

```ts
@Injectable({
  providedIn: 'root'
})
export class AuthGuard implements CanActivate {
  canActivate(): boolean {
    return true; //allow user
  }
}
```
Route configuartion :-
```ts
const routes = [
  {
    path: 'dashboard',
    component: DashboardComponent,
    canActivate: [AuthGuard]
  }
];
```

Real life example
```ts
canActivate(): boolean {
  const token = localStorage.getItem('token');
  return !!token;
}
```

Role based
```ts
canActivate(): boolean {
  const role = localStorage.getItem('role');
  return role === 'ADMIN';
}
```