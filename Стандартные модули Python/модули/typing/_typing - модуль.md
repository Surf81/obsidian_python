# Модуль `typing`
#typing #типизация #аннотация_типов #типданных 
***
В `Python 3.5 - 3.8 для аннотации типов содержимого последовательностей необходимо было пользоваться классами модуля `typing`

```python
from typing import List, Tuple, Dict, Set 
numbers: List[int] # тип всех элементов списка 
person: Tuple[str, int, bool] # тип каждого элемента кортежа 
prices: Dict[str, int] # тип ключей, тип значений answers: 
Set[float] # тип всех элементов множества
```

Начиная с Python 3.9 можно использовать стандартные классы в точно таких же целях, ничего ниоткуда не импортируя:

```python
numbers: list[int]                        # тип всех элементов списка
person: tuple[str, int, bool]             # тип каждого элемента кортежа
prices: dict[str, int]                    # тип ключей, тип значений
answers: set[float]                       # тип всех элементов множества
```

## Полезные типы модуля typing

Многие типы из модуля `typing` позволяют работать с несколькими типами одновременно. К наиболее часто используемым типам модуля `typing` относятся:
-   [Union](#Union) - параметр одного из заданных типов
-   `Optional`
-   `Any`
-   `NoReturn`

### `Union`:
Используется если параметр может содержать различный тип данных из ограниченного количества типов

```python
from typing import Union

def add_or_concatenate(a: Union[int, float, str], b: Union[int, float, str]) -> Union[int, float, str]:
    return a + b
```

Приведенный выше код можно записать в виде:

```python
from typing import Union

NumberOrStr = Union[int, float, str]

def add_or_concatenate(a: NumberOrStr, b: NumberOrStr) -> NumberOrStr:
    return a + b
```