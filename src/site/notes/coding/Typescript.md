---
{"title":"Typescript","dg-publish":true,"tags":"coding","language":"en","permalink":"/coding/typescript/","dgPassFrontmatter":true}
---

up:: [[Home/Coding\|coding]]

## About Typescript

Typescript is a strongly typed language, created and maintained by Microsoft as subset of JavaScript. It compiles to JavaScript. It is supported by all major libraries and frameworks.

Typescript is used by Vue, [[coding/React\|React]], [[coding/Angular\|Angular]].

It keeps application free from type errors, undefined and null values.



To install typescript on Windows, you can use command:

```powershell
npm install -g typescript // installs typescript globally
```

Global option reduces the risk of appearing this error:
>[!ERROR] tsc: The term 'tsc' is not recognized as a name of a cmdlet, function, script file, or executable program. Check the spelling of the name, or if a path was included, verify that the path is correct and try again.

If you want to run code made in typescript (e.g. `name.ts`), first convert it to javascript by using `tsc` command. Then you can type and execute `node name` command, which will execute converted JavaScript code.

Before using boolean in TypeScript, you need to assign a value to it. Other way you'll get an error.

## Functions

It is possible to create functions in various ways, for example:

- by declaration
  ```typescript
	function add(num1:number,num2: number): number{
	return num1 + num2
	```

- using lambda expression
	```typescript
	  const sub = (num1: number, num2: number): number => num1 - num2;
	```

- using function keyword
	```typescript
	  const mult = function(num1: number, num2: number) : number {
	  return num1 * num2
	  }
	```
## React parameter

```typescript
function add(num1: number, num2: number, ...num3: number[]): number {
return num1 + num2 + num3.reduce((a, b) => a + b, 0);
}
let numbers = [1,2,3];
console.log(add(1, 2, ...numbers));
console.log(add(1, 2, ...[1,2,3]));
console.log(add(1, 2, 1,2,3));
```

## Reduce

To calculate numbers in array you can use `reduce` function.
```typescript
function add(num1: number, num2: number, ...num3: number[]): number {
  return num1 + num2 + num3.reduce((a, b) => a + b, 0);
}

console.log(add(1, 2));
```
## Generic parameter

```typescript
function getItems<Type>(items: Type[]): Type[] {
return new Array<Type>().concat(items);
}
```
## Classes

```typescript
class Employee {
    id!: number;
    name!: string;
    address!: string;
}

let john = new Employee();
john.id = 1;
john.name = "John";
john.address = "Burkina Faso 13";
console.log(john);
```
## Constructors
In TypeScript you can't have multiple constructors. Instead, you can use either parameterless or with parameters.
```typescript
class Employee {
  id: number;
  name: string;
  address: string;

  constructor(id: number, name: string, address: string) {
    this.id = id;
    this.name = name;
    this.address = address;
  }
}

let john = new Employee(1, "John", "123 Main St");

console.log(john);
```
## Methods
Within a class you can add not only the constructor, but also methods. Example below includes interpolation   
```
`${}` 
```


```typescript
getNameWithAdress(): string {
	return `${this.name} ${this.address}`;
}
```

## Articles
| Title                                                    | Language |
| -------------------------------------------------------- | -------- |
| [[coding/Typescript questions\|Typescript questions]] | en       |

