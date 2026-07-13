# Login -

## General steps -
1. User Opens Login Page
2. User Enters Credentials
3. Client-Side Validation: Before hitting backend:
Angular validates: `Validators.required`, `Validators.email` etc
4. Login Button Clicked : `this.authService.login(credentials);`
5. Angular Sends API Request:  
`this.http.post('/login', credentials)`
6. Backend Validates Credentials, checks database.
7. Backend Generates Token
8. Angular Receives Response: 
Most production login response -
    ```json
    {
        "accessToken": "...",
        "refreshToken": "...",
        "expiresIn": 3600,
        "user": {
            "id": 1,
            "name": "Ayush",
            "email": "ayush@gmail.com",
            "role": "Admin"
        }
    }
    ```
9. Store Authentication Data: Usually stored in localStorage
10. Update Authentication state: Variables like isLoggedin, etc
11. Redirect User

---

### Typical AuthService Responsibilities
- Login : Sends login request
- Logout : Remove Token
- Store Token : Save Authentication State
- Get User : Current User Information
- Check login state : Is User Logged In?