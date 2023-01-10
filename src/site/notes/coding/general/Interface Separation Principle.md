---
{"title":"Interface Separation Principle","dg-publish":true,"tags":["coding/SOLID"],"language":"pl","permalink":"/coding/general/interface-separation-principle/","dgPassFrontmatter":true}
---

up:: [[coding/general/SOLID\|SOLID]]

## PL

Reguła separacji interfejsów powoduje, że:
- klasa dostaje tylko to, o co poprosiła, co daje większą kontrolę nad tym, jak jest używana
- zmniejsza się zależność między modułami dzięki ograniczeniu liczby metod w interfejsach
- łatwiej jest implementować interfejsy, które odpowiadają za mniej klas
Interface Separation Principle pozwala na zwiększenie bezpieczeństwa dzięki dostarczeniu tylko tych metod, które są potrzebne w danej klasie.