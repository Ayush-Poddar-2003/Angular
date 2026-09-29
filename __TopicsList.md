
## 01. Angular Fundamentals

* 1.1 What Angular Is
* 1.2 Angular Application Architecture
* 1.3 Angular CLI
* 1.4 Angular Project Structure
* 1.5 `angular.json`
* 1.6 `package.json`
* 1.7 `tsconfig.json`
* 1.8 Development vs Production Build
* 1.9 Angular Bootstrap Process
* 1.10 Angular Compiler — Basic Understanding

---

## 02. Components & Lifecycle

* 2.1 What Is a Component?
* 2.2 `@Component`
* 2.3 Component Metadata
* 2.4 Component Selector
* 2.5 Component Template
* 2.6 Component Styles
* 2.7 Component Tree
* 2.8 Component Lifecycle
* 2.9 `ngOnChanges`
* 2.10 `ngOnInit`
* 2.11 `ngDoCheck`
* 2.12 `ngAfterContentInit`
* 2.13 `ngAfterContentChecked`
* 2.14 `ngAfterViewInit`
* 2.15 `ngAfterViewChecked`
* 2.16 `ngOnDestroy`
* 2.17 Lifecycle Execution Order

---

## 03. Templates & Data Binding

* 3.1 Angular Templates
* 3.2 Interpolation
* 3.3 Property Binding
* 3.4 Attribute Binding
* 3.5 Event Binding
* 3.6 Two-Way Binding
* 3.7 Template Expressions
* 3.8 Template Reference Variables
* 3.9 `$event`
* 3.10 Property Binding vs Attribute Binding
* 3.11 Template Expression Rules

---

## 04. Directives

* 4.1 What Are Directives?
* 4.2 Component vs Directive
* 4.3 Attribute Directives
* 4.4 `ngClass`
* 4.5 `ngStyle`
* 4.6 Structural Directives
* 4.7 `*ngIf`
* 4.8 `*ngFor`
* 4.9 `ngSwitch`
* 4.10 `ng-template`
* 4.11 Creating Custom Directives
* 4.12 Directive Inputs
* 4.13 `@HostListener`
* 4.14 `@HostBinding`

---

## 05. Pipes

* 5.1 What Are Pipes?
* 5.2 Built-in Pipes
* 5.3 `date`
* 5.4 `currency`
* 5.5 `number`
* 5.6 `percent`
* 5.7 `uppercase` / `lowercase`
* 5.8 `json`
* 5.9 `async`
* 5.10 Pipe Parameters
* 5.11 Creating Custom Pipes
* 5.12 Pure Pipes
* 5.13 Impure Pipes

---

## 06. Component Communication

* 6.1 Parent → Child Communication
* 6.2 `@Input`
* 6.3 Input Changes
* 6.4 Child → Parent Communication
* 6.5 `@Output`
* 6.6 `EventEmitter`
* 6.7 Sibling Communication
* 6.8 Communication Through Shared Services
* 6.9 `@ViewChild`
* 6.10 `@ViewChildren`
* 6.11 `@ContentChild`
* 6.12 `@ContentChildren`

---

## 07. NgModules

* 7.1 Why NgModules Exist
* 7.2 `@NgModule`
* 7.3 `declarations`
* 7.4 `imports`
* 7.5 `exports`
* 7.6 `providers`
* 7.7 `bootstrap`
* 7.8 `BrowserModule`
* 7.9 `CommonModule`
* 7.10 Shared Modules
* 7.11 Core Modules
* 7.12 Feature Modules
* 7.13 Module Dependencies
* 7.14 Lazy-loaded Modules
* 7.15 Module Scope

---

## 08. Dependency Injection

* 8.1 Dependency Injection Concept
* 8.2 Injector
* 8.3 Providers
* 8.4 Services in DI
* 8.5 `providedIn`
* 8.6 Constructor Injection
* 8.7 Provider Scope
* 8.8 Hierarchical Injectors
* 8.9 `useClass`
* 8.10 `useValue`
* 8.11 `useFactory`
* 8.12 `useExisting`
* 8.13 Injection Tokens
* 8.14 `@Inject`

---

## 09. Services

* 9.1 What Is a Service?
* 9.2 Creating Services
* 9.3 Service Responsibilities
* 9.4 Component ↔ Service
* 9.5 Service ↔ Service
* 9.6 Shared Services
* 9.7 State Through Services
* 9.8 API Services
* 9.9 Utility Services
* 9.10 Service Architecture
* 9.11 Singleton Services

---

# 10. RxJS Fundamentals

* 10.1 Why RxJS?
* 10.2 Observable
* 10.3 Observer
* 10.4 Subscription
* 10.5 `next`
* 10.6 `error`
* 10.7 `complete`
* 10.8 Creating Observables
* 10.9 Subscribing
* 10.10 Unsubscribing
* 10.11 Cold Observables
* 10.12 Hot Observables
* 10.13 Subject
* 10.14 BehaviorSubject
* 10.15 ReplaySubject
* 10.16 Observable Execution

---

# 11. RxJS Operators

* 11.1 Operator Concept
* 11.2 `map`
* 11.3 `filter`
* 11.4 `tap`
* 11.5 `take`
* 11.6 `takeUntil`
* 11.7 `debounceTime`
* 11.8 `distinctUntilChanged`
* 11.9 `switchMap`
* 11.10 `mergeMap`
* 11.11 `concatMap`
* 11.12 `exhaustMap`
* 11.13 `catchError`
* 11.14 `finalize`
* 11.15 `startWith`
* 11.16 `combineLatest`
* 11.17 `forkJoin`
* 11.18 `withLatestFrom`
* 11.19 `shareReplay`
* 11.20 Operator Chaining
* 11.21 Subscription Management
* 11.22 Common RxJS Mistakes

---

# 12. HTTP & REST APIs

* 12.1 `HttpClient`
* 12.2 `HttpClientModule`
* 12.3 GET Requests
* 12.4 POST Requests
* 12.5 PUT Requests
* 12.6 PATCH Requests
* 12.7 DELETE Requests
* 12.8 Request Headers
* 12.9 Query Parameters
* 12.10 Route/API Parameters
* 12.11 Request Body
* 12.12 Typed Responses
* 12.13 HTTP Status Codes
* 12.14 HTTP Error Handling
* 12.15 API Service Pattern
* 12.16 CRUD API Integration

---

# 13. HTTP Interceptors

* 13.1 What Is an Interceptor?
* 13.2 Request Interception
* 13.3 Response Interception
* 13.4 Modifying Requests
* 13.5 Authentication Tokens
* 13.6 Global Error Handling
* 13.7 Loading Indicators
* 13.8 Multiple Interceptors
* 13.9 Interceptor Execution Order

---

# 14. Forms

* 14.1 Forms in Angular
* 14.2 Template-driven Forms
* 14.3 `ngModel`
* 14.4 Form State
* 14.5 Reactive Forms
* 14.6 `FormControl`
* 14.7 `FormGroup`
* 14.8 `FormArray`
* 14.9 Form Nesting
* 14.10 Built-in Validators
* 14.11 Custom Validators
* 14.12 Async Validators
* 14.13 `valueChanges`
* 14.14 `statusChanges`
* 14.15 Dynamic Forms
* 14.16 Form Submission
* 14.17 Form Error Handling

---

# 15. Routing

* 15.1 Angular Router
* 15.2 Route Configuration
* 15.3 `router-outlet`
* 15.4 `routerLink`
* 15.5 Route Parameters
* 15.6 Query Parameters
* 15.7 URL Fragments
* 15.8 Programmatic Navigation
* 15.9 Nested Routes
* 15.10 Child Routes
* 15.11 Route Redirects
* 15.12 Wildcard Routes
* 15.13 Lazy Loading
* 15.14 Route Data
* 15.15 Route Guards
* 15.16 `CanActivate`
* 15.17 `CanDeactivate`
* 15.18 Route Resolvers

---

# 16. Angular Material

* 16.1 Angular Material Architecture
* 16.2 Material Modules
* 16.3 Buttons
* 16.4 Inputs
* 16.5 Select
* 16.6 Checkbox
* 16.7 Radio Buttons
* 16.8 Tables
* 16.9 Sorting
* 16.10 Pagination
* 16.11 Dialog
* 16.12 Snackbar
* 16.13 Tooltip
* 16.14 Datepicker
* 16.15 Expansion Panel
* 16.16 Menus
* 16.17 Material Forms
* 16.18 Material Theming
* 16.19 Customizing Material Components

---

# 17. Angular Flex Layout

* 17.1 Flex Layout Concept
* 17.2 `fxLayout`
* 17.3 `fxLayoutAlign`
* 17.4 `fxFlex`
* 17.5 `fxFlexOrder`
* 17.6 `fxLayoutGap`
* 17.7 Responsive Layout
* 17.8 Breakpoints
* 17.9 Responsive APIs
* 17.10 Real-world Layout Patterns

---

# 18. Change Detection

* 18.1 What Is Change Detection?
* 18.2 Angular Change Detection Cycle
* 18.3 Default Change Detection
* 18.4 `OnPush`
* 18.5 Component Tree Checking
* 18.6 Object References
* 18.7 Events & Change Detection
* 18.8 Observable & Async Pipe
* 18.9 `ChangeDetectorRef`
* 18.10 `detectChanges`
* 18.11 `markForCheck`
* 18.12 Zone.js — Basic Understanding
* 18.13 Common Change Detection Problems

---

# 19. Advanced Angular

* 19.1 Content Projection
* 19.2 `ng-content`
* 19.3 `ng-template`
* 19.4 `TemplateRef`
* 19.5 `ViewContainerRef`
* 19.6 Embedded Views
* 19.7 Dynamic Components
* 19.8 `ComponentFactory`
* 19.9 Dynamic Component Creation
* 19.10 Advanced View Queries
* 19.11 Custom Form Controls
* 19.12 `ControlValueAccessor`

---

# 20. State Management

* 20.1 What Is Application State?
* 20.2 Local Component State
* 20.3 Shared State
* 20.4 State Services
* 20.5 Observable-based State
* 20.6 State Architecture
* 20.7 NgRx — When & Why
* 20.8 Store
* 20.9 Actions
* 20.10 Reducers
* 20.11 Selectors
* 20.12 Effects
* 20.13 Feature State
* 20.14 Entity

---

# 21. Angular Architecture

* 21.1 Feature-based Architecture
* 21.2 Core vs Shared
* 21.3 Feature Boundaries
* 21.4 Smart vs Presentational Components
* 21.5 Reusable Components
* 21.6 Service Layer
* 21.7 API Layer
* 21.8 State Layer
* 21.9 Dependency Direction
* 21.10 Avoiding Circular Dependencies
* 21.11 Folder Structure
* 21.12 Scalable Angular Applications

---

# 22. Testing

* 22.1 Testing Fundamentals
* 22.2 Jasmine
* 22.3 Karma
* 22.4 TestBed
* 22.5 Component Testing
* 22.6 Service Testing
* 22.7 Spies
* 22.8 Mocking
* 22.9 HTTP Testing
* 22.10 Router Testing
* 22.11 Async Testing
* 22.12 Testing Forms

---

# 23. Performance & Memory

* 23.1 Lazy Loading Optimization
* 23.2 Change Detection Optimization
* 23.3 `OnPush` Optimization
* 23.4 Subscription Optimization
* 23.5 Memory Leaks
* 23.6 Unsubscribe Strategies
* 23.7 Large Lists
* 23.8 `trackBy`
* 23.9 Virtual Scrolling
* 23.10 Bundle Optimization
* 23.11 Browser DevTools
* 23.12 Angular Performance Debugging

---

# 24. Production & Debugging

* 24.1 Angular Environment Configuration
* 24.2 Development vs Production
* 24.3 Production Builds
* 24.4 Build Configuration
* 24.5 Runtime Debugging
* 24.6 Network Debugging
* 24.7 Console Debugging
* 24.8 Source Maps
* 24.9 Common Production Issues
* 24.10 Deployment Basics
* 24.11 CI/CD Basics
* 24.12 Docker + Angular Basics

