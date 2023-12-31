# Адаптер

### Цель

Необходимо связать 2 класса чтобы вызовы и данные с 1-го класса передавались во 2-й класс.
Вызовы должны идти на 1-й класс и передаваться в методы 2-го класса. То есть вызовы в класс 1 не меняют
свою сигнатуру, остаются такими же. В итоге, функционал класса 2 используется классом 1

### Реализация

1. Создаются 2 класса так что каждый из классов наследует свой интерфейс ``export interface IObject1`` и
   ``export class Object1 implements IObject1``,  ``export interface IObject2`` и
   ``export class Object2 implements IObject2``.
   В каждом классе имеются методы ``method1`` и ``method2``
2. Создается класс-адаптер, который наследует интерфейс 1-го класса
   ``export class ObjectAdapter implements IObject1`` и который имеет в своем составе приватный объект ``#object2``
   класса 2, инициализируемом в конструкторе данного адаптера.

````js
constructor()
{
    this.#object2 = new Object2();
}
````

Адаптер 1 реализует основной вызывающий метод класса 1, указанном в интерфейсе класса 1. В данный метод
просто добавляются вызовы в методы во 2-й класс:

````js
#object2: Object2

function method1() {
    #object2.method2();
}
````