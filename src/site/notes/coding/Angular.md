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
To run application locally, use:
```typescript
ng serve -o
```

## Mono-repo
You can have multiple applications and libraries in one workspace. Applications can share code, which reduces repeating.

## Additional links

[Angular for Beginners Course (Full Front End Tutorial with Type Script)](https://www.youtube.com/watch?v=3qBXWUpoPHo)
[Add Angular 15 Missing Files. Add Angular 15 Missing Files… | by Robert Isaac | Nov, 2022 | JavaScript in Plain English](https://javascript.plainenglish.io/add-angular-15-missing-files-b90a1dbcea89)
