# Logout

End the authenticated user session and remove all authentication-related data from the application.

### <center>Authentication State Before Logout

**localStorage**:  
token = eyJhbGciOi...  
userId = 14  
role = Admin  
**Application state**: isLoggedIn = true  
**Current Route**: /dashboard

---

### What Happens When User Clicks Logout?
```
Logout Button
      ↓
AuthService.logout()
      ↓
Remove Token
      ↓
Clear User Data
      ↓
Update Auth State
      ↓
Navigate To Login
```