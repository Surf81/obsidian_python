# Модуль `gc` 
#gc #garbagecollector #оптимизация 
***
`Garbage collector` - сборщик мусора
Сборщик мусора разделяет все объекты на 3 поколения (нулевое, первое и второе). Новые объекты попадают в нулевое поколение. Если новый объект выживает в процессе сборки мусора, то он перемещается в следующее поколение. Чем старше поколение, тем реже оно сканируется на сборку мусора.
## Методы модуля `gc`
***
-   `gc.enable()`: включает сборщика мусора (по умолчанию он включен)
-   `gc.disable()`: отключает сборщика мусора
-   `gc.isenabled()`: возвращает `True`, если сборщик мусора включен, или `False` в противном случае
-   `gc.collect()`: запускает сборщика мусора на всех трех поколениях. Функция имеет необязательный аргумент `generation` (целое число от 0 до 2), указывающий номер поколения, в котором нужно запустить сборщика мусора