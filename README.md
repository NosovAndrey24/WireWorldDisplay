# WireWorldDisplay

## Скачать файл с проектом:
[Скачать проект в формате .txt](https://raw.githubusercontent.com/NosovAndrey24/WireWorldDisplay/main/8by8display.txt)

## Как расшифровать
Если вы посмотрите в текст файла, то заметите, что там есть два числа - это необходимый размер поля для проекта. Дальше идёт куча нулей и единиц - это закодированные состояния клеток. Возможно, такой формат не подойдёт для вашей программы. Но если вы имеете возможность модифицировать код вашей программы, то я предлагаю вот такой скрипт на python для расшифровки:

```python
def setstate(x, y, state):
    ''' Устанавливает состояние state в клетку с позицией (x, y) '''
    # Здесь ваш код установки состояния
    pass

with open('8by8display.txt', 'r') as file:
    numbers = list(map(int, file.read().split()))

rows = numbers.pop(0)
cols = numbers.pop(0)

x, y = 0, 0
for state in numbers:
    setstate(x, y, state)
    x += 1
    if x < cols:
        continue
    x = 0
    y += 1
    if y >= rows:
        break
```

Я, к сожалению, не знаю какой-то общепринятый формат для хранения таких проектов, поэтому оставил его в виде txt, с каким работал и сам.
