# Паттерн "Итератор"

### Цель

Реализовать возможность последовательного обхода элементов не раскрывая их общей структуры хранения

### Реализация

1. Создается интерфейс `interface IInterface` с 2-мя методами: для получения следующего
   элемента `function next(): IInterface`, самого себя, и проверки существования следующего
   элемента   `function hasNext(): boolean`
2. Реализация класса-итератора `class Iterator implements IInterface`. Итератор-класс будет иметь 2 приватные
   переменные для указания настоящего положения `index: number` и массив или любая другая структура итерируемых
   элементов `aggregates: IAggregate[]`. Метод `next(): IInterface` будет возвращать ссылку на следующий элемент,
   т.е. на самого себя
3. Инициализация итератора будет осуществляться в конструкторе передачей
   массива или другого любого составного объекта `constructor(aggregates: IAggregate{})`