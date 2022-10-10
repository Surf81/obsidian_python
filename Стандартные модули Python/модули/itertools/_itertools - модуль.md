# Модуль `itertools`
#itertools #итераторы
***
## Классы и методы модуля `itertools`
***
### Бесконечные итераторы
- **[count(start, step)](#count%20start%20step)** - итератор чисел
- **islice()**
- **[cycle(iterable)](#cycle%20iterable)** - цикличный итератор последовательности
- **[repeat(obj, times=None)](#repeat%20obj%20times%20None)** - итератор возвращает одинаковое значение

### Конечные итераторы
- **accumulate()**
- **chain**
- **compress()**
- **dropwhile()**
- **takewhile()**
- **filterfalse()**
- **groupby()**
- **starmap()**
- **tee()**
- **zip_longest()**

### Комбинаторные итераторы
- **combinations()**
- **combinations_with_replacement()**
- **product()**
- **permutations()**


### `count(start, step)`:
Возвращает бесконечный итератор чисел, начиная с `start` с шагом `step`
Аргументами могут быть любые числовые значения, допускающие операцию сложения


### `cycle(iterable)`:
Возвращает итератор, циклично генерирующий последовательность элементов переданного итерируемого объекта

Для выполнения функции `cycle()` может потребоваться значительное количество дополнительной памяти в зависимости от длины `iterable` так как для повторения цикла значения после первого прохода сохраняются в памяти!

### `repeat(obj, times=None)`:
Итератор возращает значение `obj` `times`-количество раз. Если не указано, то бесконечно


### `starmap(function, iterable1, [iterable2])`:
Функция `starmap()` используется вместо `map()` в том случае, когда элементами итерируемого объекта являются другие итерируемые объекты, скажем, кортежи, и каждый элемент этих кортежей должен быть передан в функцию `function` в качестве самостоятельного аргумента
```python
from itertools import starmap 
persons = [('Timur', 'Guev'), ('Arthur', 'Kharisov')] 
pairs = [(1, 3), (2, 5), (6, 4)] 
points = [(1, 1, 1), (1, 1, 2), (2, 2, 3)]

full_names = list(starmap(lambda name, surname: f'{name} {surname}', persons)) 

print(full_names) 
print(*starmap(lambda a, b: a + b, pairs)) 
print(*starmap(lambda x, y, z: x * y * z, points))
```
