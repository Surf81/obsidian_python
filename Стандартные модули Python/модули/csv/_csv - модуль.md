# Модуль `csv`
#csv #файлы
***
## Классы модуля `csv`
****
- **[DictReader(file, delimetr=',', quotechar='"')](#DictReader)** - чтение в список строк файла в формате словарей с ключами-именами столбцов
- **[DictWriter(file, flieldnames, delimiter, quoting)](#DictWriter%20file%20flieldnames%20delimiter%20quoting)** - Подготовка данных коллекции словарей для записи в формате `csv`
- **[reader(file, delimetr=',', quotechar='"')](#reader%20file%20delimiter%20'%20'%20quotechar%20'%20')** - чтение в список строк файла в формате списка (в матрицу). Первая строка матрицы - заголовки полей
- **[writer()](#writer)** - Подготовка данных списка для записи в формате `csv`


### `DictReader(file, delimiter=',', quotechar='"')`:
Возвращает итератор со вложенными строками-словарями с ключами-именами столбцов в формате `dict()`. Ранее версии 3.8 применялся формат `OrderedDict`

**Параметры:**
- `delimiter` - разделитель полей, по умолчанию `','`
- `quotechar` - 'упаковщик' полей (для возможности использования внутри полей символа разделителя). По умолчанию `'"'`
```python
import csv 
with open('products.csv', encoding='utf-8') as file: 
	rows = csv.DictReader(file, delimiter=';', quotechar='"') 
	for row in rows: 
		print(row)
```


### `DictWriter(file, flieldnames, delimiter, quoting)`:
Запись коллекции словарей в файл `csv`. Параметры описаны в методе [writer](#writer)

```python
import csv 
data = [{'first_name': 'Тимур', 'second_name': 'Гуев', 'class_number': 11, 'class_letter': 'А'}, 
		{'first_name': 'Руслан', 'second_name': 'Чаниев', 'class_number': 9, 'class_letter': 'Б'}, 
		{'first_name': 'Роман', 'second_name': 'Белых', 'class_number': 10, 'class_letter': 'В'}] 
columns = ['first_name', 'second_name', 'class_number', 'class_letter'] 

with open('students.csv', 'w', encoding='utf-8', newline='') as file: 
	writer = csv.DictWriter(file, fieldnames=columns, delimiter=';', quoting=csv.QUOTE_NONNUMERIC) 
	writer.writeheader() 
	for row in data: 
		writer.writerow(row)
```
**Методы:**
- **writeheader()** - запись заголовка
- **writerow()** - запись одной строки
- **writerows()** - запись коллекции строк


### `reader(file, delimiter=',', quotechar='"')`:
Возвращает итератор со строками списками list()

**Параметры:**
- `delimiter` - разделитель полей, по умолчанию `','`
- `quotechar` - 'упаковщик' полей (для возможности использования внутри полей символа разделителя). По умолчанию `'"'`
```python
import csv 
with open('products.csv', encoding='utf-8') as file: 
    rows = csv.reader(file) # создаем reader объект 
	for row in rows: 
	    print(row)
```

### `writer()`:
Преобразовывает матрицу в формат `csv`

**Параметры:**
- `delimiter` - разделитель полей, по умолчанию `','`
- `quoting` - Для задания параметра `quoting` используются специальные константы из модуля `csv`:
	-   `QUOTE_ALL`: указывает объектам записи указывать все поля
	-   `QUOTE_MINIMAL`: указывает объектам записи заключать в кавычки только те поля, которые содержат специальные символы, такие как разделитель `delimiter`, кавычка `quotechar` или любой из символов в `lineterminator`
	-   `QUOTE_NONNUMERIC`: указывает объектам записи указывать все нечисловые поля
	-   `QUOTE_NONE`: указывает объектам записи никогда не заключать в кавычки поля
```python
import csv 
columns = ['first_name', 'second_name', 'class_number', 'class_letter'] 
data = [['Тимур', 'Гуев', 11, 'А'], ['Руслан', 'Чаниев', 9, 'Б'], ['Артур', 'Харисов', 10, 'В']] 

with open('students.csv', 'w', encoding='utf-8', newline='') as file: 
	writer = csv.writer(file, delimiter=';', quoting=csv.QUOTE_NONNUMERIC)
	writer.writerow(columns) 
	for row in data: 
		writer.writerow(row)
```
**Методы:**
- **writerow()** - запись одной строки
- **writerows()** - запись коллекции строк
