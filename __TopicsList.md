
# <center> 0. Foundation Prerequisites

## 0.1 JavaScript (ES6+)

Variables & Scope
- var
- let
- const
- Hoisting
- Scope
- Closures

Functions
- Function Declarations
- Function Expressions
- Arrow Functions
- Callback Functions
- Higher Order Functions

### Arrays & Objects
- Destructuring
- Spread Operator
- Rest Operator
- Object Shorthand
- Optional Chaining
- Nullish Coalescing

### Array Methods
- map()
- filter()
- reduce()
- find()
- some()
- every()
- sort()

### Asynchronous JavaScript
- Callbacks
- Promises
- Promise Chaining
- Promise.all()
- Async/Await
- Event Loop
- Call Stack
- Microtasks vs Macrotasks

---

## 0.2 TypeScript Essentials

### Type System
- string
- number
- boolean
- any
- unknown
- never
- void

### Advanced Types
- Union Types
- Intersection Types
- Literal Types

### Interfaces & Types
- Interfaces
- Type Aliases
- Interface Extension

### Functions
- Optional Parameters
- Default Parameters
- Function Types

### Classes
- Constructors
- Methods
- Properties

### Access Modifiers
- public
- private
- protected
- readonly

### Object-Oriented Programming
- Inheritance
- Polymorphism
- Encapsulation
- Abstraction

### Advanced OOP
- Abstract Classes
- Static Members

### Generics
- Generic Functions
- Generic Interfaces
- Generic Classes

### Enums

### Decorators
- Class Decorators
- Property Decorators
- Method Decorators
- Parameter Decorators

### Utility Types
- Partial
- Pick
- Omit
- Readonly
- Record
- Required

### Type Safety
- Type Narrowing
- Type Guards
- Optional Chaining
- Nullish Coalescing

---

# <center>1. Angular Introduction & Architecture

## Angular Basics
- What is Angular
- Why Angular
- Angular vs React
- Angular vs Vue
- SPA vs MPA

## Angular Ecosystem
- Angular CLI
- Angular DevTools
- Angular Version History

## Angular Application Structure
- Root Files
- src Folder
- assets Folder
- environments
- angular.json
- package.json
- tsconfig.json

## Angular Application Lifecycle
- Application Startup Process
- Angular Compilation Process

## Bootstrapping
- main.ts
- bootstrapApplication()
- Bootstrapping Flow

---

# <center>2. Angular Modules (NgModules)

## Module Fundamentals
- What is a Module
- Why Modules Exist
- NgModule Metadata

## Types of Modules
- AppModule
- Feature Module
- Shared Module
- Core Module

## Module Organization
- Module Responsibilities
- Module Communication

## Lazy Loaded Modules

## Best Practices

---

# 3. Components Fundamentals

## Component Basics
- What is a Component
- Component Architecture
- Component Metadata

## Component Anatomy
- Class
- Template
- Style

## Selectors
- Element Selector
- Attribute Selector
- Class Selector

## Templates
- Inline Templates
- External Templates

## Styling
- Component Styles
- Global Styles

## View Encapsulation
- Emulated
- None
- ShadowDom

---

# 4. Angular Templates Deep Dive

## Template Syntax
- Expressions
- Statements

## Template Reference Variables

## Safe Navigation Operator

## Template Elements
- ng-template
- ng-container

## Content Projection
- ng-content
- Single Slot Projection
- Multi Slot Projection

## Dynamic Templates
- TemplateOutlet

---

# 5. Component Lifecycle Hooks

## Lifecycle Flow

### Initialization
- ngOnChanges
- ngOnInit

### Change Detection
- ngDoCheck

### Content Hooks
- ngAfterContentInit
- ngAfterContentChecked

### View Hooks
- ngAfterViewInit
- ngAfterViewChecked

### Cleanup
- ngOnDestroy

## Real World Use Cases

---

# 6. Data Binding & Template Syntax

## Interpolation

## Property Binding

## Attribute Binding

## Class Binding

## Style Binding

## Event Binding

## Event Object ($event)

## Two-Way Binding
- ngModel

## Change Detection Basics

---

# 7. Component Communication

## Parent to Child
- @Input()

## Child to Parent
- @Output()
- EventEmitter

## Component References
- ViewChild
- ViewChildren

## Content References
- ContentChild
- ContentChildren

## Communication Patterns
- Shared Services
- State Sharing

---

# 8. Directives

## Structural Directives
- *ngIf
- *ngFor
- *ngSwitch

## Attribute Directives
- ngClass
- ngStyle

## Custom Directives

### Directive Creation

### Host Interaction
- HostListener
- HostBinding

## Real World Examples

---

# 9. Pipes

## Pipe Basics

## Built-In Pipes
- DatePipe
- CurrencyPipe
- PercentPipe
- DecimalPipe
- JsonPipe
- SlicePipe
- AsyncPipe

## Pipe Chaining

## Custom Pipes

## Pure Pipes

## Impure Pipes

---

# 10. Services & Dependency Injection

## Services
- Why Services
- Creating Services

## Dependency Injection Basics
- Constructor Injection
- inject()

## Providers

### Provider Scope
- Root
- Module
- Component

## Singleton Services

## Advanced Dependency Injection

### Provider Types
- useClass
- useValue
- useFactory
- useExisting

### Advanced Topics
- Injector Hierarchy
- InjectionToken
- Environment Providers

---

# 11. Routing & Navigation

## Routing Fundamentals
- RouterModule
- Routes

## Router Outlet
- router-outlet

## Navigation
- RouterLink
- Router Navigate

## Route Parameters
- Route Params
- Query Params

## Child Routing

## Lazy Loading

## Route Guards
- CanActivate
- CanDeactivate
- CanMatch
- Resolve

## Advanced Routing
- Route Data
- Named Outlets
- Router Events
- Breadcrumbs
- Preloading Strategies

---

# 12. Forms

## Template Driven Forms

### Basics
- ngForm
- ngModel

### Validation
- Required
- Min Length
- Pattern

### Custom Validation

---

## Reactive Forms

### Form APIs
- FormControl
- FormGroup
- FormBuilder

### Validation
- Built-In Validators
- Custom Validators

### Advanced Forms
- FormArray
- Nested FormGroup
- Dynamic Forms
- Dynamic Validators
- Async Validators
- Cross Field Validators

---

# 13. RxJS & Observables

## RxJS Fundamentals
- Observable
- Observer
- Subscription

## Observable vs Promise

## Subscription Management
- unsubscribe()
- Memory Leak Prevention

## Core Operators
- map
- tap
- filter
- debounceTime
- catchError

## Combination Operators
- combineLatest
- forkJoin
- withLatestFrom

## Utility Operators
- distinctUntilChanged
- startWith
- takeUntil
- finalize
- shareReplay

## Higher Order Mapping

### switchMap

### mergeMap

### concatMap

### exhaustMap

## Subjects
- Subject
- BehaviorSubject
- ReplaySubject
- AsyncSubject

## Advanced RxJS Patterns

### State Management with RxJS

### Caching with shareReplay

### Debouncing API Calls

### Cancellation Patterns

---

# 14. HTTP & API Communication

## HttpClient

## CRUD Operations
- GET
- POST
- PUT
- PATCH
- DELETE

## Request Configuration
- Headers
- Params

## Error Handling

## Retry Strategies

## HTTP Interceptors

### Authentication

### Logging

### Global Error Handling

## API Layer Architecture
- API Services
- DTO Mapping
- Adapter Pattern

## Advanced HTTP
- File Upload
- File Download
- Progress Events
- Request Cancellation
- API Caching

---

# 15. Authentication & Authorization

## Authentication Basics

### Login Flow

### Logout Flow

## JWT Authentication

### JWT Structure

### Access Tokens

### Refresh Tokens

## Token Storage

### LocalStorage

### SessionStorage

### Security Concerns

## Route Protection
- Auth Guards

## Authorization
- Role Based Access
- Permission Based Access

## Authentication Interceptors

---

# 16. Angular Material

## Installation

## Themes

## Form Controls
- Input
- Select
- Checkbox
- Radio Button

## Layout Components
- Toolbar
- Sidenav

## Data Components
- Table
- Sort
- Paginator

## Dialogs
- MatDialog

## Notifications
- MatSnackBar

## Navigation
- Menu
- Tabs

## Datepicker

## Material Best Practices

---

# 17. Standalone Angular APIs

## Standalone Components

## Standalone Directives

## Standalone Pipes

## Standalone Routing

## Dependency Injection

## Bootstrapping Without NgModules

## Migration from Modules

## Modules vs Standalone

---

# 18. Angular Signals (Angular 16+)

## Signal Basics
- signal()

## Derived State
- computed()

## Side Effects
- effect()

## Signal Inputs

## Model Inputs

## Linked Signals

## Signals in Components

## Signals in Services

## Signals vs RxJS

## Best Practices

---

# 19. State Management

## When State Management is Needed

## Service Based State Management

### BehaviorSubject Pattern

### Facade Pattern

## Component Store

## NgRx Introduction

### Store

### Actions

### Reducers

### Effects

### Selectors

## Choosing a State Strategy

---

# 20. Change Detection & Performance

## Change Detection Cycle

## Default Strategy

## OnPush Strategy

## Async Pipe Optimization

## TrackBy Function

## Signal-Based Optimization

## Rendering Optimization

### Pure Pipes

### Lazy Loading

### Memoization Concepts

## Performance Best Practices

---

# 21. Angular SSR & Hydration

## Server Side Rendering

## Angular SSR

## SSR Architecture

## SEO Benefits

## Hydration

## Client Hydration

## SSR Deployment Basics

---

# 22. Project Structure & Architecture

## Enterprise Folder Structure

```text
src
 ├── core
 ├── shared
 ├── features
 ├── layouts
 ├── services
 ├── guards
 ├── interceptors
 ├── models
 ├── pipes
 ├── directives
 └── environments
```

## Feature Driven Architecture

## Smart Components

## Presentational Components

## Shared Components

## Reusable UI Design

## Facade Pattern

## Separation of Concerns

## Environment Management

## Naming Conventions

## Clean Code Principles

---

# 23. Testing

## Testing Fundamentals

## Unit Testing

## Integration Testing

## Component Testing

## Service Testing

## Pipe Testing

## Directive Testing

## Form Testing

## Observable Testing

## Mocking Dependencies

## HTTP Testing

## Jasmine

## Karma

## Jest Introduction

---

# 24. Build, Optimization & Deployment

## Angular Build Process

## Development Builds

## Production Builds

## Environment Files

## Tree Shaking

## Minification

## Bundle Optimization

## Deployment Strategies

### IIS

### Nginx

### Azure

### AWS

### Firebase

## CI/CD Basics

### GitHub Actions

### Azure DevOps

### Jenkins

---

# 25. Advanced Angular Topics

## Dynamic Components

## Dynamic Component Rendering

## Custom Form Controls

### ControlValueAccessor

## Angular Elements

## Web Components

## Progressive Web Apps (PWA)

## Web Workers

## Internationalization (i18n)

## Accessibility (a11y)

## Module Federation

## Micro Frontends

## Nx Monorepo

---

# 26. Real Production Concepts

## Logging Strategies

## Error Monitoring

## Feature Flags

## Configuration Management

## API Versioning

## Caching Strategies

## Security Best Practices

## Code Review Practices

## Git Workflow

### Branching Strategy

### Pull Requests

### Merge Conflicts

## Agile Basics

### Scrum

### Jira Workflow

---

# 27. Projects

## Beginner Projects
- Counter App
- Calculator
- Todo App

## Intermediate Projects
- Employee CRUD
- Student Management System
- Inventory Management System

## Advanced Projects
- Authentication System
- Admin Dashboard
- E-Commerce Application
- ERP Module
- HR Management System

## Production-Level Project

### Features
- Authentication
- Authorization
- Dashboard
- Reusable Components
- Reactive Forms
- State Management
- API Integration
- Lazy Loading
- Error Handling
- Unit Tests
- Deployment

---

# 28. Angular Interview Preparation

## Core Angular Questions

## TypeScript Questions

## Lifecycle Questions

## Routing Questions

## Forms Questions

## Dependency Injection Questions

## RxJS Questions

## HTTP Questions

## State Management Questions

## Change Detection Questions

## Signals Questions

## Angular Material Questions

## Architecture Questions

## Scenario Based Questions

## System Design Discussions

---

# Mastery Roadmap

## Phase 1 (Must Know for Job)
1. JavaScript
2. TypeScript
3. Components
4. Data Binding
5. Directives
6. Pipes
7. Lifecycle Hooks
8. Component Communication
9. Services & DI
10. Routing
11. Reactive Forms
12. RxJS
13. HTTP
14. Authentication
15. Angular Material

## Phase 2 (Mid-Level Developer)
16. Standalone APIs
17. Signals
18. State Management
19. Performance
20. Architecture

## Phase 3 (Senior-Level Concepts)
21. SSR
22. Testing
23. Deployment
24. Advanced Angular
25. Enterprise Architecture

---

# Final Goal

If you can confidently build a project using:

- Standalone Components
- Angular Material
- Routing
- Lazy Loading
- Reactive Forms
- Advanced RxJS
- HTTP Interceptors
- Authentication
- Authorization
- Signals
- State Management
- Testing
- Deployment

then you are genuinely **production-ready for most Angular developer roles (0–3 years experience)**.