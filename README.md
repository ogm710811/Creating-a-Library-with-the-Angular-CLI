# ExampleNg6LibApp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 6.1.4.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Project Description

Many of the improvements on Angular 6 were to the Angular CLI. The one I have really been looking forward to is the integration of the Angular CLI with ng-packagr to generate and build Angular libraries. In this project we will walk through the details of creating an Angular library.

## Project WorkSpace

Angular workspace has two projects:

### A library project

This is the library of components and services that we want to provide. This is the code that we could publish to npm for example.

### An application project

This will be a test harness for our library. Sometimes this application is used as documentation and example usage of the library.

\*\*\* There will also be a third project for End to End testing that the Angular CLI generates for us by default which we will ignore.

## Rules that will help you get your library started correctly so you won’t run into issues later.

1. ALWAYS: Create your workspace using the name of your library-app. Then rename it to the name of your library.
2. ALWAYS: Use a prefix when generating a library >>> ng generate library example-ng6-lib --prefix=enl
3. Before using our newly generated library you need to build it >>> ng build --prod example-ng6-lib
4. ALWAYS: Use the--prod flag when building your library.
5. ALWAYS: In your test application import using your library by name and NOT the individual files >>> import { ExampleNg6LibModule } from 'example-ng6-lib';

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
