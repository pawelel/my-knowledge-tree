---
{"title":"Dependency Injection","dg-publish":true,"tags":"coding","permalink":"/coding/dependency-injection/","dgPassFrontmatter":true}
---

up:: [[coding/!Coding MOC\|!Coding MOC]]

```cs
services.AddTransient<IFileManager, WindowsFileManager>();
```

## PL

Dependency injecjtion został stworzony, aby koordynować pracę większych zespołów programistycznych oraz rozwiązać problem zakodowanych na sztywno zależności między klasami. Aplikacje powinny być tworzone w formie modułów, które mogą być łatwo wymieniane i rozszerzane. Dzięki Dependency Injection możliwe jest zmniejszenie zależności między klasami przy użyciu interfejsów, dzięki czemu możliwe jest rozszerzenie funkcjonalności aplikacji bez konieczności modyfikacji istniejących klas. Jednym ze sposobów tworzenia aplikacji z użyciem DI jest Dependency Injection Container, który zawiera zbiór interfejsów i odnośników do implementacji w zależności od potrzeby klas.
Aby zmienić implementację powyższego kodu z `WindowsFileManager` na np. `LinuxFileManager`, wystarczy podmienić tylko tę jedną linijkę zamiast przepisywania kodu na nowo.

## EN

Dependency injection was created to coordinate the work of larger programming teams and solve the problem of hard-coded dependencies between classes. Applications should be created in the form of modules that can be easily replaced and extended. Thanks to Dependency Injection, it is possible to reduce the dependencies between classes using interfaces, which makes it possible to extend the functionality of the application without the need to modify existing classes. One of the ways to create applications using DI is Dependency Injection Container, which contains a set of interfaces and references to implementations depending on the need of the classes.
To change the implementation of the above code from `WindowsFileManager` to e.g. `LinuxFileManager`, just change this one line instead of rewriting the whole code.
