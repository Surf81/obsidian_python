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
- [move_to_end(key, last: bool)](#move_to_end%20key%20last%20bool)** - позволяет переместить существующий элемент либо в конец, либо в начало словаря
- **[popitem(last)](#popitem%20last%20bool%20True)** - позволяет удалить и вернуть элемент либо из конца, либо из начала словаря

### `move_to_end(key, last: bool)`:
- `key` - ключ словаря для перемещения
- `last` - значение `True` (по умолчанию) перемещает элемент в конец, значение `False` – в начало

>С помощью метода `move_to_end()` мы можем сортировать `OrderedDict` словарь по ключам.

```python
from collections import OrderedDict

letters = OrderedDict(b=2, d=4, a=1, c=3)

for key in sorted(letters):
    letters.move_to_end(key)

print(letters)
```

### `popitem(last: bool=True)`:
Возвращает кортеж из пары значений ключ-значение с начала или конца словаря и удаляет ключ из словаря
- `last` - по умолчанию `True` забирает элемент с конца. Если `False` - с начала