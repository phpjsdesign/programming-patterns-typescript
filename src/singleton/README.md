# Паттерн "Сервис"

### Цель

Необходимо гарантировать что экземпляр класса будет создан только один раз при использовании оператора `new`

### Реализация

1. Создается класс `Singleton` со статической переменной `static instance: Singleton`. 
2. Необходимый для сервиса алгоритм находится в конструкторе класса. Конструктор позволяет создавать новый экземпляр
класса, если переменная `Singleton.instance` пустая, и устанавливается содержимое переменной  `Singleton.instance`.
Если же содержимое переменной `Singleton.instance` не пустая то конструктор не доводит действие до конца и
возвращает содержимое переменной `Singleton.instance` как результат выполнения конструктора
3. При использовании сервиса оператор `new` к классу `Singleton` применяется только один раз и создается новый
объект, при последующих вызовах новый экземпляр класса не создается.