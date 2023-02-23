---
{"title":"Cannot find name Input","dg-publish":true,"tags":["coding/Angular"],"language":"en","permalink":"/coding/angular/cannot-find-name-input/","dgPassFrontmatter":true}
---

up:: [[coding/Angular/Angular\|Angular]]

If you can't compile due missing `Input` decorator name, make sure that you have it imported:
```ts
import { Component, OnInit, Input } from '@angular/core';
```
![Pasted image 20221225142836.png](/img/user/attachments/Pasted%20image%2020221225142836.png)