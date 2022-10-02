# Класс `OrderedDict` модуля [collections](_collections%20-%20модуль.md)
#OrderedDict #dict #словарь 
***
Тип `OrderedDict` является подтипом типа [dict](../../../Встроенные%20возможности%20Python/dict/_dict%20-%20тип%20данных.md), сохраняющий порядок, в котором пары "ключ-значение" вставляются в словарь. 
Когда мы перебираем объект типа `OrderedDict`, его элементы перебираются в исходном порядке. Если мы обновим значение существующего ключа, то порядок останется неизменным. Если мы удалим элемент и вставим его снова, то этот элемент будет добавлен в конец словаря.

в `Python 3.7` и более упорядоченность словаря `dict` гарантируется в отличие от предыдущих версий.

Кроме сохранения порядка `OdrededDict` отличается от обычного словаря дополнительными методами

```python
from collections import OrderedDict
numbers = OrderedDict() 
numbers['one'] = 1 
numbers['two'] = 2
numbers1 = OrderedDict({'one': 1, 'two': 2, 'three': 3}) 
numbers2 = OrderedDict([('one', 1), ('two', 2), ('three', 3)]) 
numbers3 = OrderedDict(one=1, two=2, three=3)
```

## Методы `OrderedDict`
***
- **[popitem](#popitem)** - 
- **[move_to_end()](#move_to_end)** - 

### `popitem()`:

### `move_to_end()`:
