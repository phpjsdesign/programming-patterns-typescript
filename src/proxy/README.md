# Паттерн "Прокси"

### Цель

Нужно реализовать контроль над действиями объекта не меняя при этом поведение объекта, добавляя некоторый скрытый
функционал. При этом классы должны оставаться изолированными для изменения кода, поведение начального класса мы не
меняем

### Реализация

1. Создается класс ``class Object`` с некоторыми методами ``function method1()``,  ``function method2()``
2. Создается прокси-класс ``class ProxyClass``, который имеет такие методы как и ``class Object``
   класс ``function method1()``,  ``function method2()``, включает ``Object`` класс в себя и использует методы
   класса ``Object``, добавляя скрытый дополнительный функционал (логирование, кеширование). Результат выполнения
   функций и методов прокси-класса и объекта ``Object`` одинаковые.  
