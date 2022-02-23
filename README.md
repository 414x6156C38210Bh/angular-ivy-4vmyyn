# angular-ivy-4vmyyn

[Edit on StackBlitz ⚡️](https://stackblitz.com/edit/angular-ivy-4vmyyn)

Angular new projects
npm install -g @angular/cli
ng new my-dream-app
cd my-dream-app
ng serve

npm - NodeJS package manager

npm install -g @angular/cli/latest

/home/developer/.nvm/versions/node/v12.18.1/bin/node /home/developer/.nvm/versions/node/v12.18.1/lib/node_modules/npm/bin/npx-cli.js --ignore-existing --package @angular/cli ng new angular --defaults
Node.js version v12.18.1 detected.
The Angular CLI requires a minimum Node.js version of either v12.20, v14.15, or v16.10.

1. Angular is a JavaScript framework for building reactive single-page-applications.
   The reactiveness is achieved via JavaScript changes the DOM, the HTML code during the runtime.

2. Angular versioning.
   AngularJS (Angular 1).
   Angular 2 released in 2016. A new version every 6 months. Small, incremental, backwards-compatible changes.

3. Project setup
   npm install -g @angular/cli@latest
   ng new my-first-app
   cd my-first-app
   ng serve
   http://localhost:4200

Node.NodeJS - used by the CLI to bundle the Angular project dependencies

Angular uses TypeScript, a superset of JavaScript.

7. Editing the first app
   WebStorm
   Visual Studio Code

my-first-src/index.html
<app-root></app-root>

my-first-app/src/app/
app.component.html
app.component.ts
app.module.ts

Data binding
{{component-variable-name}}

Directive - two-way data binding
[[ngModel]]="component-variable-name"

8. Course structure
   Getting Started --> the basics --> component & data binding --> directives --> services and dependency injection --> routing --> observables --> forms --> pipes --> http --> authentication --> optimizations and NgModules --> deployment --> animations and testing

9. How to get the most out of the course

10. What is TypeScript?
    it's a superscript of vanilla JS: it has types, classes, interface, it is checked at compilation time, it is compiled to JavaScript

11. A basic project setup using Bootstrap for styling

npm install --save bootstrap@latest

angular.json
"architect": {
"build": {
"styles": [
"node_modules/bootstrap/dist/css/bootstrap.min.css",
"src/styles.css"
]
... } ...}

13. Module introduction
14. How an Angular app gets loaded and Started
    index.html is the file served by the http web server
    <app-root>loading...</app-root>
    app.component.ts  
     @Component({
    selector:"app-root",
    templateUrl:"./app.component.html",
    styles:"./app.component.css"
    })
    export class AppComponent {}
    main.ts
    platformBrowserDynamic().bootstrapModule(AppModule);
    app.modules.ts
    import { BrowserModule } from '@angular/platform-browser';
    import { NgModule } from '@angular/core';
    import { FormsModule } from '@angular/forms';
    import { HttpModule } from '@angular/http';
    import { AppComponent } from './app.component';
    import { ServerComponent } from './server/server.component';
    @NgModule ({
    declarations: [
    AppComponent,
    ServerComponent
    ],
    imports: [
    BrowserModule,
    FormsModule,
    HttpModule
    ],
    providers: [],
    bootstrap: [AppComponent]
    })
    export class AppModule {}

15. Components
    business logic
    template
    styles

16. Creating a new component
    src/app/server
    server.component.ts
    import { Component } from '@angular/core';
    @Component ({ //--> this is a decorator
    selector: 'app-server',
    templateUrl: './server.component.html',
    styles: '
    })
    export class ServerComponent {

        }

    server.component.html

17. Understanding the role of AppModule and component declaration
    A module is a bundle of functionalities of the application.

18. Using custom component
    app.component.html
    <app-server></app-server>

19. Creating components with CLI and nesting components
    ng generate component servers
    ng g c servers

servers.component.html
<app-server></app-server>
<app-server></app-server>
servers.component.ts
@Component
