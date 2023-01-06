
# Форматирование строк

- **[1 Форматирование строк “По старинке” (оператор %)](#1%20Форматирование%20строк%20“По%20старинке”%20(оператор%20%))**
- 


## #1 Форматирование строк “По старинке” (оператор %)
---
```python
name = 'Bob'
print('Hello, %s' % name)
# Вывод: "Hello, Bob"
```

Несколько значений заключаются в кортеж
```python
errno = 50159747054
name = 'Bob'
print('Hey %s, there is a 0x%x error!' % (name, errno))
# 'Hey Bob, there is a 0xbadc0ffee error!'
```

Обращение по ключю словаря
```python
print(
    'Hey %(name)s, there is a 0x%(errno)x error!' % {
        "name": name, "errno": errno}
)
# Вывод: 'Hey Bob, there is a 0xbadc0ffee error!'
```

