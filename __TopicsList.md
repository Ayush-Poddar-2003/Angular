# Angular Learning Index


## 1. Introduction
- Angular overview ✅
- Angular vs AngularJS ✅
- SPA concept ✅
- Angular CLI basics ✅
- Project & folder structure ✅

---

## 2. Components
- What is a Component ✅
- Component structure (`.ts`, `.html`, `.css`) ✅
- `@Component` decorator ✅
- `selector` and where it is used ✅
- Standalone components (basics) ✅

---

## 3. Data Binding
- Interpolation (`{{ }}`) ✅
- Property Binding (`[ ]`) ✅
- Event Binding (`( )`) ✅
- Two‑Way Binding (`[(ngModel)]`) ✅
- FormsModule (basic usage) ✅

---

## 4. Directives
### Structural Directives
- What Directives are ✅
- Directive classification ✅
- `*ngIf` ✅
- `*ngFor` ✅

### Attribute Directives
- `ngClass
- `ngStyle
- `ngModel` ✅ (covered with Data Binding)

### Other Directives
- `*ngSwitch`
- Custom Directives

---

## 5. Pipes
### Core Pipes
- What Pipes are ✅
- Built‑in Pipes (date, currency, uppercase, etc.) ✅
- Pipe syntax (`{{ value | pipe }}`) ✅
- Display‑only behavior ✅
- Custom Pipe (concept) ✅

### Advanced Pipes
- Async Pipe
- Pure vs Impure Pipes

---

## 6. Services & Dependency Injection
### Core Concepts
- Why Services exist ✅
- Separation of Concerns ✅
- `@Injectable` ✅
- `providedIn: 'root'` ✅
- Dependency Injection ✅
- Constructor Injection ✅
- `inject()` awareness ✅

### Advanced Concepts
- Service scopes
- Multiple services communication

---

## 7. HTTP & APIs
### Core HTTP
- Why API calls live in Services ✅
- `HttpClient` & `HttpClientModule` ✅
- GET requests ✅
- POST requests ✅
- Observables (concept) ✅
- `subscribe()` usage ✅
- Working GET & POST flow ✅

### Advanced HTTP
- Error handling
- DELETE / PUT / PATCH
- HTTP interceptors

---

## 8. Routing
### Core Routing
- What Routing is (SPA behavior) ✅
- Routing Building Blocks ✅
- Route Configuration (`path`, `component`) ✅
- Default Route (`''`) ✅
- 404 / Wildcard Route (`**`) ✅
- Navigation (`routerLink`, programmatic) ✅
- Route Parameters (`:id`) ✅

### Advanced Routing
- Query Parameters
- Route Guards
- Auth Guards
- Child / Nested Routes
- Lazy Loading
- Route Data & Resolvers

---

## 9. Forms
### Template‑Driven Forms
- ngForm
- Validation
- Form submission flow

### Reactive Forms
- FormGroup & FormControl
- Validators
- Dynamic forms
- FormBuilder

---

## 10. Lifecycle Hooks
- `ngOnInit`
- `ngOnChanges`
- `ngOnDestroy`
- Lifecycle flow & cleanup

---

## 11. Authentication & Authorization
- Auth flow using Services
- Route protection with Guards
- Login / Logout handling

---

## 12. State & Advanced Patterns
- Shared state via Services
- Observables for state
- Basic app architecture patterns