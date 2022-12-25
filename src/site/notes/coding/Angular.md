---
{"title":"Angular","dg-publish":true,"tags":"coding","language":"en","permalink":"/coding/angular/","dgPassFrontmatter":true}
---

up:: [[Home/Coding\|Coding]]

Angular is a component-based UI framework build with [[coding/Typescript\|Typescript]] by Google.
It features:
- templates
- data binding
- forms
- routing
- observables
- PWA

Angular also supports server side rendering (SSR).

## Installation
In order to install Angular 13, use command:

```powershell
npm i @angular/cli@13.2.1 -g
```
If you want to create simple workspace without additional components, use:

```typescript
ng new workspacename --create-application false
```
To create app, you can use command
```typescript
ng new applicationname
```
To create component:
```typescript
ng g c componentname
```
- ng - angular
- g - generate
- c - component

To run application locally, use:
```typescript
ng serve -o
```

## Mono-repo
You can have multiple applications and libraries in one workspace. Applications can share code, which reduces repeating.

## Using variables
In Angular you can use interpolation with double curly braces:
```typescript
<h1>Hello {{variableName}}</h1>
```
You can also use HTML properties with variables:
```typescript
<div [innerText]="numberOfRooms"></div>
```
Which is an equivalent of JavaScripts:
```javascript
document.getElementById('numberOfRooms').innerText = numberOfRooms;
```
## Events
Angular uses `banana syntax` in event names (rounded braces):
```typescript
<button (click)="toggle()">Toggle</button>
```
## Directives
Directivves are used to change behavior and appearance of DOM elements. They can implement all lifecycle hooks and cannot have templates. They can be reusable.
>[!INFO] There are two types of directives:
>- structural
>- attribute

Examples of built-in directives:
- \*ngIf
- \*ngFor
- \*ngSwitch
- ngClass
- ngStyle
Instead of using `hidden`, you can use `*ngIf`, which can remove content from DOM until condition is met:
```ts
<div *ngIf="rooms.availableRooms > 0">
    <h2>Available rooms</h2>
</div>
```
```ts
<div [ngSwitch]="role">
  <div *ngSwitchCase="'admin'">
    <h2>Hello Admin!</h2>
    <hotelinv-rooms></hotelinv-rooms>
    </div>
  <div *ngSwitchCase="'user'">
    <h2>Hello User!</h2>
    <p>Users can view and edit their profile</p>
    </div>
  <div *ngSwitchDefault>
    <h2>Hello Guest!</h2>
 <p>You are not authorised to view content of this page.</p>
  </div>
</div>
```
Directives have two types:
	attribute
	structural
Attribute directives can't modify DOM.

## Interfaces
An interface is defined using the `interface` keyword
The `export` keyword allows to implement an interface by Classes elseware. 
```typescript
export interface IPerson {
fName: string;
}
```
Properties and methods created in the interface, *must* be created in the business object that uses this interface.
Implementation uses `implements` keyword:
```typescript
class Person implements IPerson {
public fName: string;
}
```
## Pipes
They are used for data transformation without changing actual object.
Built-in pipes:
- DatePipe
- UpperCasePipe
- LowerCasePipe
- CurrencyPipe
- DecimalPipe
- PercentPipe
- JsonPipe
- SlicePipe
- AsyncPipe

## Lifecycle hooks
- ngOnChanges
- ngOnInit
- ngDoCheck
- ngAfterContentInit
- ngAfterContentChecked
- ngAfterViewInit
- ngAgterViewChecked
- ngOnDestroy

## Additional links
[Angular - Getting started with Angular](https://angular.io/start)
[Angular for Beginners Course (Full Front End Tutorial with Type Script)](https://www.youtube.com/watch?v=3qBXWUpoPHo)
[Add Angular 15 Missing Files. Add Angular 15 Missing Files… | by Robert Isaac | Nov, 2022 | JavaScript in Plain English](https://javascript.plainenglish.io/add-angular-15-missing-files-b90a1dbcea89)
