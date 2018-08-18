# Example Angular 6 Library App

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
6. ALWAYS: Rebuild your library after making changes.

## Generating Library Components

When generating a component for our library we use the --project flag to tell the Angular CLI that we want the component generated in our library project.
command >>> ng generate component foo --project=example-ng6-lib

FOR COMPONENTS:
Using export makes the element visible.
Adding it to the entry file makes the class visible.

# Building & Packaging The Library

## Tips

1. Never directly modify the library distribution package.json.
2. ALWAYS: Use npm pack to create the tgz file.
3. Check scripts on root package.json >>> To build & package our library we can now use: npm run package.

## Using the Library in a Separate Application

Create a test workspace so you can use the library in that application.
To use the library in the new application >>> npm install ../example-ng6-lib/dist/example-ng6-lib/example-ng6-lib-0.0.1.tgz

## Tips

1. ALWAYS: Install the library’s .tgz package and NOT the directory.
2. In order to actually use a component from the library we need to add the library’s module to our App Module. To do this we make two changes in: src\app\app.module.ts
   2.1. Import the ExampleNg6LibModule >>> import { ExampleNg6LibModule } from 'example-ng6-lib';
   2.2. Add the ExampleNg6LibModule to the imports array in our AppModule.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
