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

