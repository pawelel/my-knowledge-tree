---
{"title":"Liskov Substitution Principle","dg-publish":true,"tags":"coding/SOLID","permalink":"/coding/liskov-substitution-principle/","dgPassFrontmatter":true}
---

up:: [[coding/SOLID\|SOLID]]

## PL

Reguła podstawienia Liskov polega na tym, że w przypadku podstawienia innej klasy w miejsce poprzedniej, nowa musi oferować przynajmniej te same funkcje, co poprzednia i realizować te same zadania przynajmniej tak samo dobrze.
Klasa A zawiera **kontrakt** z programistą, którego dotrzymanie jest regułą Liskov. Dotrzymanie kontraktu polega na zachowaniu przynajmniej tej samej funkcjonalności (kompatybilności).