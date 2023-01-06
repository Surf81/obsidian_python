# Модуль `heapq`
#heapq #куча #массив #двоичноедерево #очередь #очередьсприоритетом  [wiki](https://ru.wikipedia.org/wiki/Очередь_с_приоритетом_(программирование))
***

<https://docs-python.ru/standart-library/modul-heapq-python/>

## Методы модуля `heapq`

- **[`heappush()`](#heappush(heap,%20item))**
- **[`heappop()`](#`heappop(heap)`)**
- **[`heappushpop(heap, item)`](#`heappushpop(heap,%20item)`)**
- 

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
Функция `heappushpop()` добавляет значение элемента `item` в кучу `heap`, затем возвращает и удаляет самый маленький элемент из кучи `heap`.

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


