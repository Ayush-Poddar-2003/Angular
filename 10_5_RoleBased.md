## Role-Based Access Control (RBAC)

```
User Login
      ↓
JWT Contains Role/Permissions
      ↓
User Opens Page
      ↓
Check Authorization
      ↓
Allow / Deny
```

### Where Authorization Data Comes From ?
Usually from JWT.
```json
{
  "userId": 1,
  "role": "Admin"
}
```

## 401 vs 403
401 Unauthorized: User not authenticated  
403 Forbidden: User authenticated, lacks required role/permission

---
## (PBAC) Permission-Based Access Control 
Problem with RBAC,  
Manager A → Can Edit Users but  
Manager B → Cannot Edit Users

PBAC
Store permissions:
```json
{
  "role": "Manager",
  "permissions": [
    "VIEW_USERS",
    "EDIT_USERS"
  ]
}
```