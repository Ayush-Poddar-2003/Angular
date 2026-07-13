# <center> 1. XSS
Cross side scripting
> XSS happens when an attacker injects JavaScript into your application.

```
Malicious Script Injected
         ↓
Script Executes
         ↓
Reads localStorage
         ↓
Steals JWT
         ↓
Attacker Impersonates User
```
**Protection -**
1. Use Angular Template Binding
2. Avoid Direct DOM Manipulation

---

# <center> 2. CSRF
Cross-Site Request Forgery
> Attacker tricks a logged-in user into making an unwanted request.

Token in localstorage : Low CSRF Risk  
Token in Cookies : CSRF Risk Exists, because browser automatically sends cookies.

**Protection -**  
CSRF Tokens, SameSite Cookies, Double Submit Cookies, Handle with backend team

# <center> 3. HTTPS
Without HTTPS: Network Traffic Visible  
With HTTPS
Data becomes encrypted during transport.
