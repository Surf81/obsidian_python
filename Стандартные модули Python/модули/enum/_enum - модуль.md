# Модуль `enum`
#enum #перечисления
***

Модуль определяет четыре класса перечисления, которые могут использоваться для определения уникальных множеств имён и значений: `Enum`, `IntEnum`, `Flag` и `IntFlag`. Он также определяет один декоратор, `unique()` и один вспомогательный класс — `auto`.

### _class_ `Enum`
Базовый класс для создания перечисляемых констант. Альтернативный синтаксис построения см. в разделе [Функциональный API](https://digitology.tech/docs/python_3/library/enum.html#api).

### _class_ `IntEnum`
Базовый класс для создания перечисляемых констант, которые также являются подклассами `int`.

### _class_ `IntFlag`
Базовый класс для создания нумерованных констант, которые можно комбинировать с помощью побитовых операторов, не теряя своего членства в `IntFlag`. Поля `IntFlag` также являются подклассами `int`.

### _class_ `Flag`
Базовый класс для создания нумерованных констант, которые можно комбинировать с помощью побитовых операций без потери принадлежности к `Flag`

### `unique`()
Декоратор класса Enum, который обеспечивает привязку только одного имени к любому значению.

### _class_ `auto`
Экземпляры заменяются соответствующим значением для полей Enum. Начальное значение начинается с 1.
<br><br>
## Создание `Enum`


```python
from enum import Enum
class Color(Enum):
    RED = 1
    GREEN = 2
    BLUE = 3
```

Перечисления поддерживают итерацию в порядке определения:

```python
class Shake(Enum):
    VANILLA = 7
    CHOCOLATE = 4
    COOKIES = 9
    MINT = 3

for shake in Shake:
    print(shake)

# Shake.VANILLA
# Shake.CHOCOLATE
# Shake.COOKIES
# Shake.MINT
```

Поля перечисления хэшируемы, поэтому они могут использоваться в словарях и множествах:

```python
apples = {}
apples[Color.RED] = 'red delicious'
apples[Color.GREEN] = 'granny smith'
apples == {Color.RED: 'red delicious', Color.GREEN: 'granny smith'}
# True
```
<br><br>
## Доступ к полям перечисления и атрибутам


```python
# Получения перечисления по значению
Color(1)
# <Color.RED: 1>

# Если вы хотите получить доступ к полям перечисления по _имени_, используйте доступ к элементам:

Color['RED']
# <Color.RED: 1>

# Если у вас есть поле перечисления и вам нужно его `name` или `value`:
member = Color.RED
member.name
# 'RED'
member.value
# 1
```
<br><br>
## Обеспечение уникальных значений перечисления

По умолчанию перечисления позволяют использовать несколько имен в качестве псевдонимов для одного и того же значения. Когда такое поведение нежелательно, можно использовать декоратор `unique`, чтобы гарантировать, что каждое значение используется только один раз в перечислении:

Если будут найдены дубли, то вызывается ValueError с подробностями:

```python
from enum import Enum, unique

@unique
class Mistake(Enum):
    ONE = 1
    TWO = 2
    THREE = 3
    FOUR = 3

# Traceback (most recent call last):

# ValueError: duplicate values found in <enum 'Mistake'>: FOUR -> THREE
```
<br><br>
## Использование автоматических значений

Если точное значение неважно, можно использовать `auto`:

```python
from enum import Enum, auto
class Color(Enum):
    RED = auto()
    BLUE = auto()
    GREEN = auto()

list(Color)
# [<Color.RED: 1>, <Color.BLUE: 2>, <Color.GREEN: 3>]
```

Значения выбираются `_generate_next_value_()`, которые могут быть переопределены:

```python
class AutoName(Enum):
    def _generate_next_value_(name, start, count, last_values):
        return name
class Ordinal(AutoName):
    NORTH = auto()
    SOUTH = auto()
    EAST = auto()
    WEST = auto()
list(Ordinal)
# [<Ordinal.NORTH: 'NORTH'>, <Ordinal.SOUTH: 'SOUTH'>, <Ordinal.EAST: 'EAST'>, <Ordinal.WEST: 'WEST'>]
```
<br><br>

Подробнее про Enum:

https://digitology.tech/docs/python_3/library/enum.html#api