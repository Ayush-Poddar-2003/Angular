# Interface 
An interface defines the shape (structure) of an object.

It tells TypeScript:
- what properties an object should have
- what type those properties should be

It does NOT contain implementation, only structure.

```ts
interface User {
  id: number;
  name: string;
  email: string;
}
```

# Interface with API Response

```ts
getUsers(){
 return this.http.get<User[]>('api/users');
}
```

Sometimes properties are not mandatory.
Use ?

```ts
interface User {
  id: number;
  name: string;
  phone?: string;
}
```