# Класс `defaultdict` модуля [collections](_collections%20-%20модуль.md)
#defaultdict #словарь #удобство
***
### defaultdict(type, \*\*kwargs):
Создает словарь с предустановленными значениями заранее не определенных ключей, а так же с предопределенными ключами.
Все методы доступные для обычных словарей (тип [dict](../../../Встроенные%20возможности%20Python/dict/_dict%20-%20тип%20данных.md)), также доступны и для `defaultdict` словарей.

**Примечание:**
- можно сравнивать обычные словари (тип `dict`) и `defaultdict` словари.
- При создании `defaultdict` словаря можно указывать не только тип данных для значений по умолчанию, но и любую функцию, **не принимающую аргументов** и **возвращающую некоторое дефолтное значение**
- Тип `defaultdict` работает быстрее чем использование методов `setdefault()` и `get()` обычного словаря (тип `dict`).

#### атрибут `default_factory`:
Возвращает тип значения по умолчанию и позволяет изменить его
from collections import defaultdict

a = defaultdict(int)
print(a.default_factory)
a.default_factory = list
print(a.default_factory)

```python
from collections import defaultdict 

info = defaultdict(int, {'name': 'Timur', 'age': 29, 'job': 'Teacher'}) 
info1 = defaultdict(int, name='Timur', age=29, job='Teacher') 
info2 = defaultdict(int, [('name', 'Timur'), ('age', 29), ('job', 'Teacher')])

print(info['name'])      # Timur
print(info['salary'])    # 0 т.к. ключ не определен, по умолчанию указан `int`
```

```python
from collections import defaultdict 
info = defaultdict(lambda: '1000000$', {'name': 'Timur', 'age': 29, 'job': 'Teacher'}) 
print(info['name']) 
print(info['salary'])   # выведет 1000000$
```
