# Модуль `heapq`
#heapq #куча #массив #двоичноедерево #очередь #очередьсприоритетом  [wiki](https://ru.wikipedia.org/wiki/Очередь_с_приоритетом_(программирование))
***

<https://docs-python.ru/standart-library/modul-heapq-python/>

## Функции модуля `heapq`

- **[`heappush()`](#heappush(heap,%20item))**
- **[`heappop()`](#`heappop(heap)`)**
- **[`heappushpop(heap, item)`](#`heappushpop(heap,%20item)`)**
- **[`heapify()`](#`heapify(x)`)**
- **[`heapreplace()`](#`heapreplace(heap,%20item)`)**
- **[`merge()`](#`merge(*iterables,%20key=None,%20reverse=False)`)**
- **[`nlargest()`](#`nlargest(n,%20iterable,%20key=None)`)**
- **[`nsmallest()`](#`nsmallest(n,%20iterable,%20key=None)`)**

## Алгоритм очереди кучи.

Модуль `heapq` обеспечивает реализацию алгоритма очереди кучи, также известного как алгоритм очереди приоритетов.

Кучи - это двоичные деревья, для которых каждый родительский узел имеет значение, меньшее или равное любому из его дочерних элементов. В этой реализации используются массивы, для которых `heap[k] <= heap[2*k+1]` и `heap[k] <= heap[2*k+2]` для всех `k`, считая элементы с нуля. Для сравнения, несуществующие элементы считаются бесконечными. Интересным свойством кучи является то, что ее наименьшим элементом всегда является корень `heap[0]`.

Приведенный ниже API отличается от алгоритмов кучи, описанных в учебниках в двух аспектах:

1.  Модуль `heapq` использует индексацию с нуля. Это делает связь между индексом для узла и индексами для его дочерних элементов несколько менее очевидной, но является более подходящей, поскольку Python использует индексацию с нуля.
2.  Метод `pop()` модуля `heapq` возвращает наименьший элемент, а не самый большой. В учебниках он называется `min heap`. Элемент `max heap` чаще встречается в учебниках из-за его пригодности для сортировки на месте.

Эти два аспекта позволяют просматривать кучу как обычный список Python без сюрпризов: `heap[0]` - самый маленький элемент, а `heap.sort()` поддерживает инвариант кучи!

Чтобы создать кучу, используйте инициализацию [списка](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tip-dannyh-list-spisok/ "Список list в Python.") `[]`, или можно преобразовать заполненный список в кучу с помощью функции [`heapq.heapify()`](https://docs-python.ru/standart-library/modul-heapq-python/funktsija-heapify-modulja-heapq/ "Функция heapify() модуля heapq в Python.").

#### `heappush(heap, item)`
Функция [`heappush()`](https://docs-python.ru/standart-library/modul-heapq-python/funktsija-heappush-modulja-heapq/ "Функция heappush() модуля heapq в Python.") модуля [`heapq`](https://docs-python.ru/standart-library/modul-heapq-python/ "Модуль heapq, кучи в Python.") добавляет значение элемента `item` в кучу `heap`, сохраняя инвариант кучи.
```python
h = []
heapq.heappush(h, (5, 'write code'))
heapq.heappush(h, (7, 'release product'))
heapq.heappush(h, (1, 'write spec'))
heapq.heappush(h, (3, 'create tests'))
print(h)
#>>> [(1, 'write spec'), (3, 'create tests'), (5, 'write code'), (7, 'release product')]
print(h[0])
#>>> (1, 'write spec')
```


#### `heappop(heap)`
Функция `heappop()` возвращает и удаляет наименьший элемент из кучи `heap`, сохраняя инвариант кучи.

Если куча `heap` пуста, то поднимается [исключение `IndexError`](https://docs-python.ru/tutorial/vstroennye-iskljuchenija-interpretator-python/vstroennye-iskljuchenija/ "Исключения наследуемые от Exception в Python.").

Чтобы получить доступ к наименьшему элементу, не выталкивая его, используйте `heap[0]`


#### `heappushpop(heap, item)`
Функция `heappushpop()` сначала добавляет значение элемента `item` в кучу `heap`, затем возвращает и удаляет самый маленький элемент из кучи `heap`.

Комбинация push/pop функция `heapq.heappushpop()` возвращает меньшее из двух значений, оставляя большее значение в куче.

Комбинированное действие выполняется более эффективно, чем вызов `heapq.heappush()`, за которым следует отдельный вызов `heapq.heappop()`.


#### `heapify(x)`
Функция `heapify()` преобразовывает список `x` в кучу на месте за линейное время.
```python
import heapq
h = [1, 3, 5, 7, 9, 2, 4, 6, 8, 0]
heapq.heapify(h)
print(h)
#>>> [0, 1, 3, 2, 6, 9, 5, 4, 7, 8]
```


#### `heapreplace(heap, item)`
Функция `heapreplace()` сначала удаляет и возвращает наименьший элемент из кучи `heap`, а потом добавляет новый элемент `item`. Размер кучи `heap` не меняется. Если куча пуста, поднимается [исключение `IndexError`](https://docs-python.ru/tutorial/vstroennye-iskljuchenija-interpretator-python/vstroennye-iskljuchenija/ "Исключения наследуемые от Exception в Python.").

Эта одношаговая операция более эффективна, чем вызов `heapq.heappop()`, за которой следует `heapq.heappush()` и может быть более подходящей при использовании кучи фиксированного размера. Комбинация pop/push всегда возвращает элемент из кучи и заменяет его на `item`.

Возвращаемое значение может быть больше, чем добавленный элемент. Если это нежелательно, рассмотрите возможность использования функции [`heapq.heappushpop()`](https://docs-python.ru/standart-library/modul-heapq-python/funktsija-heappushpop-modulja-heapq/ "Функция heappushpop() модуля heapq в Python."). Его комбинация push/pop возвращает меньшее из двух значений, оставляя большее значение в куче.


#### `merge(*iterables, key=None, reverse=False)`
Функция `merge()` объединяет несколько отсортированных последовательностей `*iterables` в один отсортированный итератор. Например, объединить записи с метками времени из нескольких файлов журнала. Возвращает итератор для отсортированных значений.

Функция `heapq.merge()` ведет себя аналогично `sorted` как функция `itertools.chain(*iterables)`, но возвращает итерируемую [последовательность](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tipy-posledovatelnostej/ "Типы последовательностей в Python."), не извлекает сразу данные в память и предполагает, что каждый из входных потоков `iterables` уже отсортирован от наименьшего к наибольшему.

Имеет два необязательных аргумента, которые должны быть указаны как ключевые аргументы.

-   Аргумент `key` определяет ключевую функцию, принимающую один аргумент, которая используется для извлечения ключа сравнения из каждого входного элемента. Значением по умолчанию является `None`, что означает сравнение элементов напрямую.
-   Аргумент `reverse` - это [логическое значение](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/bool-logicheskij-tip-dannyh/ "Логический тип данных bool в Python."). Если установлено значение `True`, то входные элементы объединяются, как если бы каждое сравнение было обратным. Чтобы добиться поведения, подобного сортированному `itertools.chain(*iterables), reverse=True`, все [итерируемые](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tip-dannyh-iterator-iterator/ "Итератор Iterator, протокол итератора в Python.") элементы должны быть отсортированы от наибольшего к наименьшему.
```python
first_list = sorted([45, 12, 63, 95])
second_list = sorted([42, 13, 69, 54, 15])
final_list = list(heapq.merge(first_list, second_list))
#>>> [12, 13, 15, 42, 45, 54, 63, 69, 95]
```


#### `nlargest(n, iterable, key=None)`
Функция `nlargest()` возвращает список с `n` самыми большими элементами из набора данных, определенного с помощью итерируемой [последовательности](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tipy-posledovatelnostej/ "Типы последовательностей в Python.") `iterable`.

Аргумент `key`, если он указан, определяет [функцию](https://docs-python.ru/tutorial/opredelenie-funktsij-python/ "Функции в Python, определение функций.") с одним аргументом, которая используется для извлечения ключа сравнения из каждого элемента в итерируемой [последовательности](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tipy-posledovatelnostej/ "Типы последовательностей в Python.") `iterable`, например `key=str.lower`. Значением по умолчанию является `None`, что означает сравнение элементов напрямую.

Функция `nlargest()` эквивалентна вызову `sorted(iterable, key=key, reverse=True)[:n]`.

Работает лучше для маленьких значений `n`. Для больших значений более эффективно использовать функцию `sorted()`. Также, когда `n=1`, более эффективно использовать [встроенную функцию `max()`](https://docs-python.ru/tutorial/vstroennye-funktsii-interpretatora-python/funktsija-max/ "Функция max() в Python, максимальное значение элемента.").

Если требуется повторное использование функции `heapq.nlargest()`, рассмотрите возможность преобразования последовательности `iterable` в реальную [кучу](https://docs-python.ru/standart-library/modul-heapq-python/ "Модуль heapq, кучи в Python.").


#### `nsmallest(n, iterable, key=None)`
Функция `nsmallest()` возвращает список с `n` наименьшими элементами из набора данных, определенного с помощью итерируемой [последовательности](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tipy-posledovatelnostej/ "Типы последовательностей в Python.") `iterable`.

Аргумент `key`, если он указан, определяет [функцию](https://docs-python.ru/tutorial/opredelenie-funktsij-python/ "Функции в Python, определение функций.") с одним аргументом, которая используется для извлечения ключа сравнения из каждого элемента в итерируемой [последовательности](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tipy-posledovatelnostej/ "Типы последовательностей в Python.") `iterable`, например `key=str.lower`. Значением по умолчанию является `None`, что означает сравнение элементов напрямую.

Функция `nsmallest()` эквивалентна вызову `sorted(iterable, key=key)[:n]`.

Работает лучше для маленьких значений `n`. Для больших значений более эффективно использовать функцию `sorted()`. Также, когда `n=1`, более эффективно использовать [встроенную функцию `min()`](https://docs-python.ru/tutorial/vstroennye-funktsii-interpretatora-python/funktsija-min/ "Функция min() в Python, минимальное значение элемента.").

Если требуется повторное использование функции `heapq.nsmallest()`, рассмотрите возможность преобразования последовательности `iterable` в реальную [кучу](https://docs-python.ru/standart-library/modul-heapq-python/ "Модуль heapq, кучи в Python.").


