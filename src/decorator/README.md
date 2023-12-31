# Паттерн "Декоратор"

### Цель

Динамически добавлять объектам и функциям дополнительную функциональность. Должен быть какой-то статичный шаблонная
функция или класс, которые умеют принимать объекты и функции при конструировании и в итоге шаблон выполняет программные
коды с новыми поведениями

### Реализация

1. Создается функция-обертка, которая принимает различные значения и объекты в конструкторе. Список допустимых
   значений объектов и переменных определяется заранее. Сама функция может описываться следующим образом

   ```ts
   function wrapper(value1: IValue | number, value2: IValue | number) {
   }
   ```
   И эта функция выполняет операции с переданными значениями. При этом может использоваться внутренний объект

   ```ts
   return new _Wrapper(value1, value2)
   ```

2. Создаются интерфейсы для передачи в объекты-конструкторы `IValue` и их реализации-классы.