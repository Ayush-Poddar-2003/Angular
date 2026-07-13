# Token Storage
Where should we store tokens like access & refresh?

---
## <center> 1. localStorage
> A browser-provided storage area that allows applications to store data as key-value pairs.  

Storage : lifetime, even after refresh, browser/system restart, Until manually removed

**How Data Is Stored ?**  
Everything is stored as strings.  
`localStorage.setItem('token', 'abc123');`  
`token = abc123` is stored in local memory.

**Storing Objects -**
Objects must be converted to JSON.
```js
const user = {
  id: 1,
  name: 'Ayush'
};
// converting user to json first
localStorage.setItem('user', JSON.stringify(user));
```
Retrieving :
`JSON.parse(localStorage.getItem('user'));`

#### Common Operations :-
1. Save Data : `localStorage.setItem('token', token);`
2. Read Data : `localStorage.getItem('token');`
3. Remove Data : `localStorage.removeItem('token');`
4. Clear Everything : `localStorage.clear();` - Used during logout.

**Flow -**  
Backend returns --access token--> Angular stores --> API Call --> Interceptor reads token --> Sends `Authorization: Bearer abc123`

#### Security Risks :-
1. XSS Attack : attacker injects JavaScript into your application, `localStorage.getItem('token');` and steals token

> Usually AuthService wraps localStorage.

```
AuthService
 ├── saveToken()
 ├── getToken()
 └── removeToken()
```

---
## <center>2. Session Storage
> Browser storage that stores key-value pairs only for the current browser tab/session.

```
Refresh Page ✅
Close Tab ❌
Close Browser ❌
Data Removed
```

**Common Operations-**
1. Save Token : `sessionStorage.setItem('token', token);`
2. Get Token : `sessionStorage.getItem('token');`
3. Remove Token : `sessionStorage.removeItem('token');`
4. Clear Everything : `sessionStorage.clear();`

> Still Vulnerable to XSS

### 3. Memory Storage
> Store token inside: AuthService, Signal, BehaviorSubject etc

Best security, Worst user experience.

### 4. HttpOnly Cookies
> Token stored by browser cookie.