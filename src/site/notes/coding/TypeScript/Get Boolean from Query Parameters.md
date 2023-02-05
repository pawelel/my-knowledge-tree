---
{"title":"Get Boolean from Query Parameters","dg-publish":true,"tags":["coding/TypeScript"],"language":"en","permalink":"/coding/type-script/get-boolean-from-query-parameters/","dgPassFrontmatter":true}
---

up:: [[coding/TypeScript/TypeScript\|TypeScript]]

You can get value from the query string and assign a Boolean using ternary operator:

```ts
const hasDiscount = new URLSearchParams(window.location.search).get('discount');
const discount = (hasDiscount === 'true'|| hasDiscount === '1') ? true : false;
}
```
