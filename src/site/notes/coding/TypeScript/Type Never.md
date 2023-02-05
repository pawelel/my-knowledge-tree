---
{"title":"Type Never","dg-publish":true,"tags":["coding/TypeScript"],"language":"en","permalink":"/coding/type-script/type-never/","dgPassFrontmatter":true}
---

up:: [[coding/TypeScript/TypeScript\|TypeScript]]

It is possible to secure else statement using never type. You can add similar line at the end of your code. It should be never executed. If something will be added before, there will be an error:

```ts
else{
const neverGoHere: never = something; // something is some unhandled value
console.log(neverGoHere);
}
```