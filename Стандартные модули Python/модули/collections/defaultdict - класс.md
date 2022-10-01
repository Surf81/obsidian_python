# Класс `defaultdict` модуля [collections](_collections%20-%20модуль.md)
#defaultdict #словарь #удобство
***
### defaultdict(type, \*args, \*\*kwargs):
Создает словарь с предустановленными значениями заранее не определенных ключей, а так же с предопределенными ключами
```python
from collections import defaultdict 

info = defaultdict(int, {'name': 'Timur', 'age': 29, 'job': 'Teacher'}) 
info1 = defaultdict(int, name='Timur', age=29, job='Teacher') 
info2 = defaultdict(int, [('name', 'Timur'), ('age', 29), ('job', 'Teacher')])

print(info['name']) print(info['salary'])
```