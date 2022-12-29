---
{"title":"Reguła podstawiania Liskov","dg-publish":true,"tags":"coding/SOLID","language":"pl","permalink":"/coding/regula-podstawiania-liskov/","dgPassFrontmatter":true}
---

up:: [[coding/SOLID\|SOLID]]
alt:: [[coding/Liskov Substitution Principle\|Liskov Substitution Principle]]
Reguła podstawienia Liskov polega na tym, że w przypadku podstawienia innej klasy w miejsce poprzedniej, nowa musi oferować przynajmniej te same funkcje, co poprzednia i realizować te same zadania przynajmniej tak samo dobrze.
Klasa A zawiera **kontrakt** z programistą, którego dotrzymanie jest regułą Liskov. Dotrzymanie kontraktu polega na zachowaniu przynajmniej tej samej funkcjonalności (kompatybilności).
