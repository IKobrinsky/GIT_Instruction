## Операции с изменениями в репозитории

### Работа с локальным репозиторием

Для того, чтобы добавить под версионный контроль существующие файлы, нужно запустить команду `git add` несколько раз, указав индексируемые файлы, а затем выполнив `git commit`:
```
$ git add *.c
$ git add LICENSE
$ git commit -m 'Initial project version'
```

Параметр -m указывает сообщение, которое будет отображаться в коммите.

В дальнейшем изменения файлов, которые уже были добавлены в индекс, так же производятся командой `git commit`. Если не требуется, чтобы в коммит попали все текущие изменения, можно использовать параметр -F для  указания отдельных файлов, подлежащих обработке.

### Игнорирование файлов

Добиться того, чтобы некоторые файлы не попадали в коммит можно так же при помощи игнорирование файлов. Оно настраивается в файле *.gitignore* в виде набора шаблонов имен файлов, не подлежащих отслеживанию.

Основаные правила синтаксиса файла *.gitignore*:

+ Одна строчка - одно правило
+ Пустые строки игнорируются
+ Комментарии доступны через решётку(#) в начале строки
+ Символ "/" в начале строки указывает, что правило применяется только к файлам и папкам, которые располагаются в той же папке, что и сам файл *.gitignore*
+ Доступно использовать спецсимволы: звёздочка(*) заменяет любое количество символов(ноль или больше), вопросик(?) заменяет от нуля до одного символа. Можно размещать в любом месте правила
+ Две звёздочки(**) используются для указания любого количества поддиректорий,
+ Восклицательный знак(!) в начале строки означает инвертирование правила, необходим для указания исключений из правил игнорирования,
+ Символ "\\" используется для экранирования спецсимволов
+ Для игнорирования всей директории, правило должно оканчиваться на слэш(/), в противном случае правило считается именем файла.

### Работа с удаленным репозиторием.

Если вы работаете с удаленным репозиторием, то локальные изменения нужно передавать при помощи команды
```
git push 
```
Если кроме вас есть и другие разработчики, использующие этот репозиторий, то нужно перед тем, как передавать свои изменения, нужно получить последние изменения из удаленного репозитория в локальную копию. Это можно сделать командой
```
git pull
```
или последовательным вызовом команд
```
git fetch 
git merge
```
Первая команда получает список изменений удаленного репозитория, вторая вносит эти изменения в локальный репозиторий.

### Определение состояния файлов

 Для определения, какие файлы в каком состоянии находятся, нужно выполнить команду
 ```
git status
  ```
  Результатом выполнения команды будет список измененных индексированных файлов и список неотслеживаемых файлов. Кроме того, если вы используете [ветвление](./branches.md), то команда сообщает на какой ветке вы находитесь и сообщает вам, расходится ли она с основной веткой.

  [Назад](repository_operations.md) [Вперед](./changeset_info.md) [К содержанию](./readme.md)