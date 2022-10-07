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
- [Any](#Any) - любой тип
- [Callable](#Callable) - функция
- [NoReturn](#NoReturn) - всегда отсутствующее значение функции
- [Optional](#Optional) - конкретный тип или `None`
- [TypeAlias](#TypeAlias) - псевдоним для другого типа
- [Union](#Union) - параметр одного из заданных типов

### `Any`:
Может возникнуть ситуация, когда не получается указать какой-либо конкретный тип, потому что, функция может принимать на вход абсолютно что угодно. Для этих случаев тоже есть специальный тип `Any`:

```python
from typing import Any

def func(arg: Any) -> Any:
    return arg
```

Таким образом любой тип совместим с типом `Any`, как и `Any` совместим с любым типом.


### `Callable`:
`Callable[[int], str]` это функция с параметром (int) -> str.


### `Literal`:
Значение принадлежит ограниченному списоку



### `NoReturn`:
Специальный тип `NoReturn` указывает, что функция никогда не возвращает значение:

```python
from typing import NoReturn

def stop() -> NoReturn:
    raise RuntimeError('no way')
```


### `Optional`:
Используется если параметр может содержать значение определенного типа, либо `None`. Мы можем использовать тип `Union` следующим образом:

```python
from typing import Union

name: Union[str, None]
```

Однако это настолько частая ситуация, что для этого ввели отдельный тип `Optional`:

```python
from typing import Optional

name: Optional[str]
```


### `TypeAlias`:
Для явного обозначения псевдонима типа

```python
from typing import Union

NumberOrStr : TypeAlias = Union[int, float, str]

def add_or_concatenate(a: NumberOrStr, b: NumberOrStr) -> NumberOrStr:
    return a + b
```


### `Union`:
Используется если параметр может содержать различный тип данных из ограниченного количества типов.
В Python 3.10 вместо записи `Union[X, Y]` можно писать `X | Y`.

```python
from typing import Union

def add_or_concatenate(a: Union[int, float, str], b: Union[int, float, str]) -> Union[int, float, str]:
    return a + b
```

Приведенный выше код можно записать в виде:

```python
from typing import Union

NumberOrStr : TypeAlias = Union[int, float, str]

def add_or_concatenate(a: NumberOrStr, b: NumberOrStr) -> NumberOrStr:
    return a + b
```