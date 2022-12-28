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

## Articles

| Title                                                                                                      | Language |
| ---------------------------------------------------------------------------------------------------------- | -------- |
| [[coding/Angular for beginners Course by Santosh Yadav\|Angular for beginners Course by Santosh Yadav]] | en       |
| [[coding/Cannot find name Input\|Cannot find name Input]]                                               | en       |

---
title: Angular
dg-publish: true
tags: coding
language: en
---
up:: [[Home/Coding\|coding]]

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

Constructor should be used for services injection, lifecycle hook for any blocking code.

## Component interaction
Components can interact using:
- `@Input` and `@Output`
- `@ViewChild` and `@ContentChild`
- Services

Properties shouldn't be mutated.
Instead of pushing an array:
```ts
 this.roomList.push(newRoom);
```
use:
```ts
this.roomList = [...this.roomList, newRoom];
```
which creates a new object.

## ChangeDirectionStrategy
By default detection strategy is set to CheckAlways, which in some cases can impact on applications performance. You can use CheckOnce strategy using `OnPush`. OnPush deactivates automatic change detection and applies to all child directives. It cannot be overriden, however change detection can be explicitly invoked.

## On Changes
`ngOnChanges` lifecycle hook can be applied with `@Input` decorator. It can be used whenever you want to control updated data or change direction strategy through a service.

## Do Check
`ngDoCheck` listens every change, which is costly for an application. Also shouldn't be used along with ngOnChanges.

```ngAfterViewInit() {
console.log()
}
```

## View Child
It is possible to use child component inside of another one using `@ViewChild` instead of `@Input` decorator. It requires additional import and implement - `AfterViewInit`
```ts
import { Component, OnInit, ViewChild, AfterViewInit } from '@angular/core';
```
```ts
export class RoomsComponent implements OnInit, AfterViewInit {
```
```ts
 @ViewChild(HeaderComponent) headerComponent: HeaderComponent | undefined;
```
```ts
  ngAfterViewInit() {
    console.log(this.headerComponent);
  }
```
By default `@VievChild` is set to `{static: false}`

## Dependency injection
In Angular dependency can be a class or an object which you can inject inside a component or service. It is one of the Angulars core features.
There are class based providers, value providers and factories.

> [!INFO] It is recommended to keep components a small as possible and try to split code into multiple services.

To generate services, use:
```ts
ng g s rooms
```
where g stands for genarate, s for service, rooms - service name

Services should not be accessible from template. Therefore you should use `private` access modifier in a component:
```ts
constructor(private roomsService: RoomsService) {}
```
And then
```ts
  ngOnInit(): void {
  this.roomList = this.roomsService.getRooms();
  }
```
Component should not have access to services logic.

If you need to use annother service instance, add providers to a `@Component`:
```ts
@Component({
  selector: 'hotelinv-rooms',
  templateUrl: './rooms.component.html',
  styleUrls: ['./rooms.component.scss'],
  providers: [RoomsService]
})
```

## Additional links
[Angular - Getting started with Angular](https://angular.io/start)
[Add Angular 15 Missing Files. Add Angular 15 Missing Files… | by Robert Isaac | Nov, 2022 | JavaScript in Plain English](https://javascript.plainenglish.io/add-angular-15-missing-files-b90a1dbcea89)
