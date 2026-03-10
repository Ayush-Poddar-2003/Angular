# INTRODUCTION

### ANGULAR ?   
Released in 2010 by Google  
Created by Misko Hevery and Adam Abrons  
Originally called AngularJS(Depreciated), currently we use Angular  
A JS Framework, Based on MVC Architecture.  


---
INSTALLATION ?

Go to https://angular.dev/installation  

Install Angular CLI (@angular/cli) once using  
`npm install -g @angular/cli`   
-g means global

Verify using 
`ng version`

---
### For Every New Project:-
Go to that folder  
`ng new <ProjectName>`  
`cd <ProjectName>`  
`ng serve`  To run server  
It will run on 
 http://localhost:4200/

---
### REACT Vs ANGULAR  
    npm create vite@latest → ng new  
    npm run dev            → ng serve  
    Dev server default port:  
      Vite → 5173  
      Angular → 4200

---
### FILE & FOLDER STRUCTURE :-  

Root Level :-

![alt text](image-3.png)

- .vscode : VS Code settings for this project only.  
- node_modules : All installed dependencies.
- public : Static assets.
- src: Inside src:
    - main.ts → Entry point (bootstraps Angular app)
    - index.html → Main HTML file
    - styles.css → Global styles
    - app → Your real application code
- .editorconfig : Controls indentation rules for the project.
- .prettierrc : Formatting rules (if using Prettier).
- angular.json : Angular project configuration.
- package.json
- tsconfig.app.json : TypeScript config specifically for app files.
- tsconfig.json : TypeScript configuration. 
- tsconfig.spec.json : TypeScript config for test files.             

---
 # ANGULAR CLI {Command Line Interface}
 > Command Line Interface for Angular.

 Tool that helps developers  
 Create, build, test, and deploy angular applications.  

---
### WHY WE NEED IT ?
Angular projects have:
- Strict structure
- Multiple config files
- TypeScript setup
- Build configuration
- CLI automates all that.

Without CLI → setup would take 1–2 hours manually.  
With CLI → 1 command.

---
TO INSTALL  
`npm install -g @angular/cli` once globally

TO CHECK IF INSTALLED  
`ng version`

CREATING A NEW APPLICATION EVERYTIME  
`ng new <AppName>`

TO SEE ALL ng commands  
`ng help`  

