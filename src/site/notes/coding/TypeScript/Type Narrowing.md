---
{"title":"Type Narrowing","dg-publish":true,"tags":["coding/TypeScript"],"language":"en","permalink":"/coding/type-script/type-narrowing/","dgPassFrontmatter":true}
---

up:: [[coding/TypeScript/TypeScript\|TypeScript]]

It is possible to perform action on a specific type:

```ts
// simulated server response
let get = (response: unknown) => response;

const logFixed = (v: number)=>{
// fixed-point notation (in this case without the floating point)
console.log(v.toFixed());
};

// unknown type
let value = get(3.5);

// check, if a type is a number
if(typeof value === "number") {
logFixed(value);
}
```
