# Модуль `json`
#json #файлы 
***
## Классы и методы модуля `json`
***
- **[dump(data, file)](#dump%20data%20file)** - сериализует объект и записывает в файл
- **[dumps(data)](#dumps%20data)** - сериализует объект и возвращает в виде строки
- **[load(file)](#load%20file)** - считывает из файла и десериализует в словарь
- **[loads(str)](#loads%20str)** - десериализует строку в словарь dict()

### `dump(data, file)`:
Сериализует объект `data` и записывает в файловый объект `file`
В формат JSON нельзя записать словарь, у которого ключи – кортежи.

**Необязательные аргументы** `indent`, `sort_keys` и `separators`:
-  `indent` задает отступ от левого края. По умолчанию имеет значение `None`. Может быть числом или строкой. Если строка - она подставляется в начало
-  `sort_keys` задает сортировку ключей в результирующем `json`. По умолчанию имеет значение `False`
-  `separators` задает кортеж, состоящий из двух элементов `(item_separator, key_separator)`, которые представляют разделители для элементов и ключей.  По умолчанию аргумент имеет значение `(', ', ': ')`.
-  `skipkeys` можно игнорировать ключи не подходящего формата, например кортежи. По умолчанию False
- `ensure_ascii` - можно отменить декодирование киррилических символов. По умолчанию True (декодирование включено) - нужно для совместимости с другими языками программирования

```python
import json 
data = {'name': 'Russia', 'phone_code': 7, 'capital': 'Moscow', 'currency': 'RUB'} with open('contries.json', 'w') as file: 
	json.dump(data, file)
```

### `dumps(data)`:
Возвращает строку в формате `json` поученную из сериализованного объекта `data`
В формат JSON нельзя записать словарь, у которого ключи – кортежи.

Дополнительные аргументы аналогичны [dump(data, file)](#dump%20data%20file)
```python
import json

data = {'name': 'Russia', 'phone_code': 7, 'capital': 'Moscow', 'currency': 'RUB'}

json_data = json.dumps(data)            # сериализуем словарь data в json строку

print(type(json_data))
print(json_data)
```

выводит:

```no-highlight
<class 'str'>
{"name": "Russia", "phone_code": 7, "capital": "Moscow", "currency": "RUB"}
```

### `load(file)`:
Читает объект `json` из файла и десериализует его в словарь
```python
import json 
with open('data.json') as file: 
	data = json.load(file) # передаем файловый объект 
	for key, value in data.items(): 
		if type(value) == list: 
			print(f'{key}: {", ".join(value)}') 
		else: 
			print(f'{key}: {value}')
```

### `loads(str)`:
Преобразует строку в формате `json` в словарь `dict()`
В случае если строка для десериализации содержит данные с ошибкой, то модуль `json` не сможет правильно прочитать такую строку, и программа завершится с ошибкой.
```python
import json

json_data = '{"name": "Russia", "phone_code": 7, "capital": "Moscow", "currency": "RUB"}'

data = json.loads(json_data)
print(type(data))
print(data)
```

выводит:

```no-highlight
<class 'dict'>
{'name': 'Russia', 'phone_code': 7, 'capital': 'Moscow', 'currency': 'RUB'}
```
