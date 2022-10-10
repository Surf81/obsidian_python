# Модуль `itertools`
#itertools #итераторы
***
## Классы и методы модуля `itertools`
***
### Бесконечные итераторы
- **[count(start, step)](#count%20start%200%20step%201)** - итератор чисел
- **[islice(iterator, count)](#islice%20iterator%20count)** - ограничитель бесконечного итератора
- **[cycle(iterable)](#cycle%20iterable)** - цикличный итератор последовательности
- **[repeat(obj, times=None)](#repeat%20obj%20times%20None)** - итератор возвращает одинаковое значение

### Конечные итераторы
- **[accumulate()](#accumulate%20iterable)** - аналог `reduce()` возвращающий в т.ч. промежуточные результаты
- **chain**
- **compress()**
- **dropwhile()**
- **takewhile()**
- **filterfalse()**
- **groupby()**
- **[starmap(function, iterable1, \[iterable2\])](#starmap%20function%20iterable1%20iterable2)** - аналог map() умеющий работать с вложенными последовательностями
- **tee()**
- **zip_longest()**

### Комбинаторные итераторы
- **combinations()**
- **combinations_with_replacement()**
- **product()**
- **permutations()**


### `accumulate(iterable)`:
Функция `accumulate()` возвращает итератор, элементами которого являются накопленные суммы или накопленные результаты функции `func`.

Аргументы функции:
-   `iterable` — итерируемый объект
-   `func` — функция, принимающая два аргумента, по умолчанию используется функция сложения `operator.add`
-   `initial` — начальное значение, по умолчанию имеет значение `None`

Функция работает аналогично функции `reduce()` за тем исключением, что функция `accumulate()` генерирует все промежуточные результаты, а не только конечный.

### `count(start=0, step=1)`:
Возвращает бесконечный итератор чисел, начиная с `start` с шагом `step`
Аргументами могут быть любые числовые значения, допускающие операцию сложения


### `cycle(iterable)`:
Возвращает итератор, циклично генерирующий последовательность элементов переданного итерируемого объекта

Для выполнения функции `cycle()` может потребоваться значительное количество дополнительной памяти в зависимости от длины `iterable` так как для повторения цикла значения после первого прохода сохраняются в памяти!

### `islice(iterator, count)`:
Вспомогательная функция для бесконечного итератора. Позволяет ограничить бесконечный итератор ограниченным количеством итераций
```python
from itertools import islice, count
for i in islice(count(10), 5):   # ограничение на 5 итераций
     print(i)
```


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
# в отличие от map() starmap() умеет распаковывать последовательности

print(full_names) 
print(*starmap(lambda a, b: a + b, pairs)) 
print(*starmap(lambda x, y, z: x * y * z, points))
```
