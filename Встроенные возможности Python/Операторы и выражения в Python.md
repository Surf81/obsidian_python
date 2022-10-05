# Операторы и выражения в `Python`
#операторы #выражения [исходный текст](https://pythonchik.ru/osnovy/operatory-i-vyrazheniya-v-python)
***
## Операторы сравнения[](https://pythonchik.ru/osnovy/operatory-i-vyrazheniya-v-python#operatory-sravneniya)

Рассмотрим простой пример — `1 + 2 == 3`.

Для проверки истинности данного условия, используется логический тип. Когда мы выполним данное выражение, в результате нам вернется `True` (истина) или `False` (ложь).

```python
>>> 1 + 2 == 3
True
```

![](https://pythonchik.ru/static/native/netologyPython/star1.svg)![](https://pythonchik.ru/static/native/netologyPython/star1.svg)![](https://pythonchik.ru/static/native/netologyPython/star2.svg)![](https://pythonchik.ru/static/native/netologyPython/owner.svg)

Онлайн-курс "Python-разработчик с нуля"

![](https://pythonchik.ru/static/native/netologyPython/money.svg "credit")

4 125 руб./месяц

![](https://pythonchik.ru/static/native/netologyPython/time.svg "time")

12 месяцев

![](https://pythonchik.ru/static/native/netologyPython/flashActive.svg)![](https://pythonchik.ru/static/native/netologyPython/flash.svg)

Освойте Python и начните работать через 6 меcяцев

![](https://pythonchik.ru/static/native/netologyPython/flashActive.svg)![](https://pythonchik.ru/static/native/netologyPython/flash.svg)

Добавьте 3 работоспособных проекта в портфолио

![](https://pythonchik.ru/static/native/netologyPython/flashActive.svg)![](https://pythonchik.ru/static/native/netologyPython/flash.svg)

Получите опыт работы в команде

[Перейти](https://go.redav.online/f1da53803a5dfa70)

В данном примере мы используем один из операторов сравнения — "==" (равно). Всего в Python таких операторов 6:

-   `==` — равно;
-   `!=` — не равно;
-   `>` — больше;
-   `<` — меньше;
-   `>=` — больше или равно;
-   `<=` — меньше или равно.

```python
>>> 1 == 2
False
>>> 1 != 2
True
>>> 1 > 2
False
>>> 1 < 2
True
>>> 1 >= 2
False
>>> 1 <= 2
True
```

## Логические операторы[](https://pythonchik.ru/osnovy/operatory-i-vyrazheniya-v-python#logicheskie-operatory)

Правила выполнения логических операций соответствуют [таблицам истинности](https://ru.wikipedia.org/wiki/%D0%A2%D0%B0%D0%B1%D0%BB%D0%B8%D1%86%D0%B0_%D0%B8%D1%81%D1%82%D0%B8%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8). В Python 3 логических оператора:

-   `or` — логическое "ИЛИ";
-   `and` — логическое "И";
-   `not` — логическое отрицание.

```python
>>> (1 + 1 == 2) or (2 * 2 == 5)
True
>>> (1 + 1 == 2) and (2 * 2 == 5)
False
>>> (1 + 1 == 2) and not (2 * 2 == 5)
True
```

## Арифметические операторы[](https://pythonchik.ru/osnovy/operatory-i-vyrazheniya-v-python#arifmeticheskie-operatory)

Арифметические операторы в Python производят арифметические операции над числами (сложение, вычитание, деление и т.д.);

-   `+` — сложение;
-   `-` — вычитание;
-   `*` — умножение;
-   `/` — деление;
-   `//` — целочисленное деление (возвращает только целую часть от деления, значение после запятой отбрасывается);
-   `%` — деление по модулю (возвращает остаток от деления);
-   `**` — возведение в степень.

```python
>>> 1 + 2
3
>>> 1 - 2
-1
>>> 1 * 2
2
>>> 1 / 2
0.5
>>> 10 // 3
3
>>> 10 % 3
1
>>> 3 ** 2
9
```

[](https://practicum.yandex.ru/backend-developer/?utm_source=yandex&utm_medium=cpc&utm_campaign=Yan_Net_RF_Pyth_Kursy-exp-tgo1-4_460&utm_content=sty_context%3As_pythonchik.ru%3Acid_66390989%3Agid_4717091926%3Apid_34411505154%3Aaid_12438186354%3Acrid_0%3Arid_%3Ap_0%3Apty_none%3Amty_%3Amkw_%3Adty_desktop%3Acgcid_0%3Arn_%D0%92%D0%BE%D1%80%D0%BE%D0%BD%D0%B5%D0%B6%3Arid_193&utm_term=%D0%BF%D0%B8%D1%82%D0%BE%D0%BD%20%D1%83%D1%87%D0%B8%D1%82%D1%8C&_openstat=ZGlyZWN0LnlhbmRleC5ydTs2NjM5MDk4OTsxMjQzODE4NjM1NDtweXRob25jaGlrLnJ1Omd1YXJhbnRlZQ&yclid=8170768257172897791&stat-id=11&test-tag=442553430235665&banner-sizes=eyI3MjA1NzYwNjQ3NjExNDM5OCI6Ijc1MHgyMzIifQ%3D%3D&format-type=118&actual-format=10&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjcxMjcyMSJ9&order-banners-options=eyI3MjA1NzYwNjQ3NjExNDM5OCI6MjA0OH0&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=232#short-program)

[![](https://favicon.yandex.net/favicon/practicum.yandex.ru?size=32&stub=2)

practicum.yandex.ru



](https://yandex.ru/an/count/W_mejI_zODy3bHy0j3PYdeXu67j3nGK0tmGndgyzOm00000uujL9XfFitvZMxPkV0O01Zl3od0M80OBCrvY00P01lAVzrTo0W802c06yf_tLNA01vAMe0UIb_TLSk06iySYI8y010jW1chFNdW7W0SBEfPK1w04a-07cZgQRvHYv0lZspq6fPtuEy0AvrEIM3T1ag0COnmNu1F3uqm681Q2UnG6G1V3uqm6W1SxKGAW5bl4ri0MMyJMu1PRnDS05aSYE0yW5cgfbq0M1xXA7A9CqL03VRQa7VSEmq318Jr6u1xG6Y821me201k08qyso3EW9LkSERU3mu3_92W3mFnQg2n3d-X71VSC008co0G5CwkWBj9ET0V0B2uWCvlVUlW7e39y6c0sepYhW3OA0W860W808FuVHpAJ3Yi3lRQ0EzFWw_ORpdOw6qgTHW13DbzGVa12_WvdagRsBeeB0i13u4AgSthqMu17Xu9G6w17dzEt-hQJwm9jGEFL0XbU53_u_143f4ftSiyceiZjmy189auUuwhdGqeONu1EMyJM0582W0eWKbhk7zjEGkAzfe1IMyJMe5F3uqm6m58lyoJEu5C2KtW_05830qU4Zo1G2q1JfflWLs1IYbuoP1k0K0UWKZ0B85TZC-8Ez1D0L_OkicGRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5kRtthu1s1Q15vWNX9x7AwWN2RWN0S0NjPO1q1VGXWFO5xQdFUWN0w0O5B0OmRNscGQu60RG627u6AQ7xOpkZQxIrG606R3qkEBGlP6v88aPN9y90000002W6O83g1cg-lYL1B0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a3w1dk1V0PWC83-1cde8KTWHh__zDsS6PaSOWQm8Gzc1hnmBG1i1hbYDY6jfMNZkC1k1e3zHe10000c1kzrIsm6rsu6mJf6m000A1xlA51y1lCkuQN0lWRezgNPO8S3K9IEJfNTaP9T35kOpVO7BIJdG7W7F3uqm7f7F4S0008aC4Opp-07Vz_cHt87S24FU0TgwW7aHwe7W7G7kYVY_-UqRMeX07O7lhQ7eWV____0Q0VpPVK7x0V0SWVpTchJz8V1ZOsCJ8uDTaVu1_e7u0W0eWW3AaWi224W23W80RG8V__0O0YGB0Y0SWY0YaWSGI9Ov1aKg89jm5KC-9Bn1FOBdOLnF4SZOKayGZPEQS8nX5HRAR0tRXXbWXEi8VtnHqapCNXyjzfBjr9iYv5rWPMBkfpqtrTFjwETS0L-KwIhZnT181vxg5roOOsAmQ0gtwFDTFjZAcq4H-c9YnQBwV3g5hHuw4pipikHTvBkKHje_40~1?stat-id=11&test-tag=442553430235665&banner-sizes=eyI3MjA1NzYwNjQ3NjExNDM5OCI6Ijc1MHgyMzIifQ%3D%3D&format-type=118&actual-format=10&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjcxMjcyMSJ9&order-banners-options=eyI3MjA1NzYwNjQ3NjExNDM5OCI6MjA0OH0&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=232)РЕКЛАМА

[

Программирование на Python — курс от Яндекса

](https://yandex.ru/an/count/W_mejI_zODy3bHy0j3PYdeXu67j3nGK0tmGndgyzOm00000uujL9XfFitvZMxPkV0O01Zl3od0M80OBCrvY00P01lAVzrTo0W802c06yf_tLNA01vAMe0UIb_TLSk06iySYI8y010jW1chFNdW7W0SBEfPK1w04a-07cZgQRvHYv0lZspq6fPtuEy0AvrEIM3T1ag0COnmNu1F3uqm681Q2UnG6G1V3uqm6W1SxKGAW5bl4ri0MMyJMu1PRnDS05aSYE0yW5cgfbq0M1xXA7A9CqL03VRQa7VSEmq318Jr6u1xG6Y821me201k08qyso3EW9LkSERU3mu3_92W3mFnQg2n3d-X71VSC008co0G5CwkWBj9ET0V0B2uWCvlVUlW7e39y6c0sepYhW3OA0W860W808FuVHpAJ3Yi3lRQ0EzFWw_ORpdOw6qgTHW13DbzGVa12_WvdagRsBeeB0i13u4AgSthqMu17Xu9G6w17dzEt-hQJwm9jGEFL0XbU53_u_143f4ftSiyceiZjmy189auUuwhdGqeONu1EMyJM0582W0eWKbhk7zjEGkAzfe1IMyJMe5F3uqm6m58lyoJEu5C2KtW_05830qU4Zo1G2q1JfflWLs1IYbuoP1k0K0UWKZ0B85TZC-8Ez1D0L_OkicGRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5kRtthu1s1Q15vWNX9x7AwWN2RWN0S0NjPO1q1VGXWFO5xQdFUWN0w0O5B0OmRNscGQu60RG627u6AQ7xOpkZQxIrG606R3qkEBGlP6v88aPN9y90000002W6O83g1cg-lYL1B0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a3w1dk1V0PWC83-1cde8KTWHh__zDsS6PaSOWQm8Gzc1hnmBG1i1hbYDY6jfMNZkC1k1e3zHe10000c1kzrIsm6rsu6mJf6m000A1xlA51y1lCkuQN0lWRezgNPO8S3K9IEJfNTaP9T35kOpVO7BIJdG7W7F3uqm7f7F4S0008aC4Opp-07Vz_cHt87S24FU0TgwW7aHwe7W7G7kYVY_-UqRMeX07O7lhQ7eWV____0Q0VpPVK7x0V0SWVpTchJz8V1ZOsCJ8uDTaVu1_e7u0W0eWW3AaWi224W23W80RG8V__0O0YGB0Y0SWY0YaWSGI9Ov1aKg89jm5KC-9Bn1FOBdOLnF4SZOKayGZPEQS8nX5HRAR0tRXXbWXEi8VtnHqapCNXyjzfBjr9iYv5rWPMBkfpqtrTFjwETS0L-KwIhZnT181vxg5roOOsAmQ0gtwFDTFjZAcq4H-c9YnQBwV3g5hHuw4pipikHTvBkKHje_40~1?stat-id=11&test-tag=442553430235665&banner-sizes=eyI3MjA1NzYwNjQ3NjExNDM5OCI6Ijc1MHgyMzIifQ%3D%3D&format-type=118&actual-format=10&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjcxMjcyMSJ9&order-banners-options=eyI3MjA1NzYwNjQ3NjExNDM5OCI6MjA0OH0&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=232)

[

Обучаем Python-разработчиков с нуля в Практикуме. 20 часов практики – бесплатно.

](https://yandex.ru/an/count/W_mejI_zODy3bHy0j3PYdeXu67j3nGK0tmGndgyzOm00000uujL9XfFitvZMxPkV0O01Zl3od0M80OBCrvY00P01lAVzrTo0W802c06yf_tLNA01vAMe0UIb_TLSk06iySYI8y010jW1chFNdW7W0SBEfPK1w04a-07cZgQRvHYv0lZspq6fPtuEy0AvrEIM3T1ag0COnmNu1F3uqm681Q2UnG6G1V3uqm6W1SxKGAW5bl4ri0MMyJMu1PRnDS05aSYE0yW5cgfbq0M1xXA7A9CqL03VRQa7VSEmq318Jr6u1xG6Y821me201k08qyso3EW9LkSERU3mu3_92W3mFnQg2n3d-X71VSC008co0G5CwkWBj9ET0V0B2uWCvlVUlW7e39y6c0sepYhW3OA0W860W808FuVHpAJ3Yi3lRQ0EzFWw_ORpdOw6qgTHW13DbzGVa12_WvdagRsBeeB0i13u4AgSthqMu17Xu9G6w17dzEt-hQJwm9jGEFL0XbU53_u_143f4ftSiyceiZjmy189auUuwhdGqeONu1EMyJM0582W0eWKbhk7zjEGkAzfe1IMyJMe5F3uqm6m58lyoJEu5C2KtW_05830qU4Zo1G2q1JfflWLs1IYbuoP1k0K0UWKZ0B85TZC-8Ez1D0L_OkicGRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5kRtthu1s1Q15vWNX9x7AwWN2RWN0S0NjPO1q1VGXWFO5xQdFUWN0w0O5B0OmRNscGQu60RG627u6AQ7xOpkZQxIrG606R3qkEBGlP6v88aPN9y90000002W6O83g1cg-lYL1B0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a3w1dk1V0PWC83-1cde8KTWHh__zDsS6PaSOWQm8Gzc1hnmBG1i1hbYDY6jfMNZkC1k1e3zHe10000c1kzrIsm6rsu6mJf6m000A1xlA51y1lCkuQN0lWRezgNPO8S3K9IEJfNTaP9T35kOpVO7BIJdG7W7F3uqm7f7F4S0008aC4Opp-07Vz_cHt87S24FU0TgwW7aHwe7W7G7kYVY_-UqRMeX07O7lhQ7eWV____0Q0VpPVK7x0V0SWVpTchJz8V1ZOsCJ8uDTaVu1_e7u0W0eWW3AaWi224W23W80RG8V__0O0YGB0Y0SWY0YaWSGI9Ov1aKg89jm5KC-9Bn1FOBdOLnF4SZOKayGZPEQS8nX5HRAR0tRXXbWXEi8VtnHqapCNXyjzfBjr9iYv5rWPMBkfpqtrTFjwETS0L-KwIhZnT181vxg5roOOsAmQ0gtwFDTFjZAcq4H-c9YnQBwV3g5hHuw4pipikHTvBkKHje_40~1?stat-id=11&test-tag=442553430235665&banner-sizes=eyI3MjA1NzYwNjQ3NjExNDM5OCI6Ijc1MHgyMzIifQ%3D%3D&format-type=118&actual-format=10&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjcxMjcyMSJ9&order-banners-options=eyI3MjA1NzYwNjQ3NjExNDM5OCI6MjA0OH0&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=232)

[Узнать больше](https://yandex.ru/an/count/W_mejI_zODy3bHy0j3PYdeXu67j3nGK0tmGndgyzOm00000uujL9XfFitvZMxPkV0O01Zl3od0M80OBCrvY00P01lAVzrTo0W802c06yf_tLNA01vAMe0UIb_TLSk06iySYI8y010jW1chFNdW7W0SBEfPK1w04a-07cZgQRvHYv0lZspq6fPtuEy0AvrEIM3T1ag0COnmNu1F3uqm681Q2UnG6G1V3uqm6W1SxKGAW5bl4ri0MMyJMu1PRnDS05aSYE0yW5cgfbq0M1xXA7A9CqL03VRQa7VSEmq318Jr6u1xG6Y821me201k08qyso3EW9LkSERU3mu3_92W3mFnQg2n3d-X71VSC008co0G5CwkWBj9ET0V0B2uWCvlVUlW7e39y6c0sepYhW3OA0W860W808FuVHpAJ3Yi3lRQ0EzFWw_ORpdOw6qgTHW13DbzGVa12_WvdagRsBeeB0i13u4AgSthqMu17Xu9G6w17dzEt-hQJwm9jGEFL0XbU53_u_143f4ftSiyceiZjmy189auUuwhdGqeONu1EMyJM0582W0eWKbhk7zjEGkAzfe1IMyJMe5F3uqm6m58lyoJEu5C2KtW_05830qU4Zo1G2q1JfflWLs1IYbuoP1k0K0UWKZ0B85TZC-8Ez1D0L_OkicGRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5kRtthu1s1Q15vWNX9x7AwWN2RWN0S0NjPO1q1VGXWFO5xQdFUWN0w0O5B0OmRNscGQu60RG627u6AQ7xOpkZQxIrG606R3qkEBGlP6v88aPN9y90000002W6O83g1cg-lYL1B0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a3w1dk1V0PWC83-1cde8KTWHh__zDsS6PaSOWQm8Gzc1hnmBG1i1hbYDY6jfMNZkC1k1e3zHe10000c1kzrIsm6rsu6mJf6m000A1xlA51y1lCkuQN0lWRezgNPO8S3K9IEJfNTaP9T35kOpVO7BIJdG7W7F3uqm7f7F4S0008aC4Opp-07Vz_cHt87S24FU0TgwW7aHwe7W7G7kYVY_-UqRMeX07O7lhQ7eWV____0Q0VpPVK7x0V0SWVpTchJz8V1ZOsCJ8uDTaVu1_e7u0W0eWW3AaWi224W23W80RG8V__0O0YGB0Y0SWY0YaWSGI9Ov1aKg89jm5KC-9Bn1FOBdOLnF4SZOKayGZPEQS8nX5HRAR0tRXXbWXEi8VtnHqapCNXyjzfBjr9iYv5rWPMBkfpqtrTFjwETS0L-KwIhZnT181vxg5roOOsAmQ0gtwFDTFjZAcq4H-c9YnQBwV3g5hHuw4pipikHTvBkKHje_40~1?stat-id=11&test-tag=442553430235665&banner-sizes=eyI3MjA1NzYwNjQ3NjExNDM5OCI6Ijc1MHgyMzIifQ%3D%3D&format-type=118&actual-format=10&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjcxMjcyMSJ9&order-banners-options=eyI3MjA1NzYwNjQ3NjExNDM5OCI6MjA0OH0&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=232)

## Операторы присваивания[](https://pythonchik.ru/osnovy/operatory-i-vyrazheniya-v-python#operatory-prisvaivaniya)

Операторы присваивания в Python работаю вполне очевидно — значение находящееся справа присваивается переменной, находящейся слева. Существует несколько разновидностей операторов присваивания:

-   `=` — значение правого операнда присвоится левому операнду;
-   `+=` — сумма левого и правого операнда присвоится левому операнду;
-   `-=` — разность левого и правого операнда присвоится левому операнду;
-   `*=` — произведение левого и правого операнда присвоится левому операнду;
-   `/=` — разделит левый операнд на правый и результат присвоится левому операнду;
-   `//=` — результат целочисленного деления левого операнда на правый операнд присвоится левому операнду;
-   `%=` — разделит левый операнд на правый по модулю и результат присвоится левому операнду;
-   `**=` — возведет левый операнд в степень правого и результат присвоится левому операнду.

```python
>>> a = 10
>>> print(a)
10

>>> a = 10
>>> a += 1  # аналогично a = a + 1
>>> print(a)
11

>>> a = 10
>>> a -= 2  # аналогично a = a - 2
>>> print(a)
8

>>> a = 10
>>> a *= 2  # аналогично a = a * 2
>>> print(a)
20

>>> a = 10
>>> a /= 2  # аналогично a = a / 2
>>> print(a)
5.0

>>> a = 10
>>> a //= 3  # аналогично a = a // 2
>>> print(a)
3

>>> a = 10
>>> a %= 3  # аналогично a = a % 2
>>> print(a)
1

>>> a = 10
>>> a **= 2  # аналогично a = a ** 2
>>> print(a)
100
```

Python поддерживает не только обычное присваивание правого операнда левому, но и множественное присваивание.

![Множественное присваивание в Python](https://pythonchik.ru/pic/lb1/intext_4ce03f20-636c-428f-89dc-3d630142055b_original.svg)

Множественное присваивание в Python

```python
>>> a, b, c = 1, "python", [1,2,3]
>>> print(a, b, c)
1 python [1, 2, 3]
```

С помощью такого присваивания можно поменять значения переменных между собой:

```python
>>> a = 1
>>> b = 2
>>> a, b = b, a
>>> print(a, b)
2 1
```

Также с помощью множественного присваивания можно "распаковывать" строки (str), списки (list), кортежи (tuple) и словари (dict).

[

![](https://avatars.mds.yandex.net/get-yabs_performance/6557685/2a000001830ce5dfd4ff10117d0c703d8924/huge)





](https://yandex.ru/an/count/X1CejI_zOEm3JI00T3XDy-EryUyD0WK0x0GnfAyzOm00000uujL9wCknyzY8oAkQ0O01_hTmY07-jt2G0OR7ifBZyzYL1A01ji7MgTo0W802g06smTQfNB01qAJd1xW1siV3_IJ00GBO0TRJivm1u06QwAgK0UW12FW1vexUlW680WUW0jJAl1Qv0lZspq6fPtuEm0B-jt3m0io7jOSAq6Ie0nYg0VW4dvtl0OW5nzEw0P05dvtl0Q05Ylv8g0M8wJom1OZfFBW5YEaym0Nfh9q1o0N6W2ZG1UAa5U05jOSeapHK0DzjgGTzmr3ifabFKRW7mWlG1n3O1mg9me200k08ggMU2-W91sD4Qf81f_S_oGwg2n0FqMuYVSC00BOvNm5CwkWBnzEw0V0B2uWCvexUlW7e39y6c0sepYhW3OA0W860W808FuVHpAJ3Yi3lRQ0Em8Gz_OQ3xk-qqgTHW13hfy8Ua12_WvdagRsBeeB0i13G4DM6hr_u4AgSthqMu17iwvG7w17teAxq_hZlwWrWOq1X48EbRmRzF-aIdTopoQYoEt3m4WcJXxZgkT3IXXVW4uhTEO0KW82028WKrF3vZ-N3mPJc0Q0KYjqvg1JRX-C1i1JmtyWek1IWdR0C0j0Kw_MbRzWKi9_vc0RW507e58m2q1Mmd_cO1l0LmOhsxAEFlFnZe1RmligP1h0MemV95j0MvexUlW7O5e4Nc1U0vPuhg1S9k1S1m1UrbW7G5z260zWNzU8-w1S4e1W5i1Z1jVQP1hWODT0O8VWOfeVjZEwDhjBL0O0PiFIuuj2zaRaWYHbSdma000000A0PWWEm6RWPmD8P4dbXOdDVSsLoTcLoBt8tCZajC-0P1EWPxWNm6O320u4Q__ypptw1PT-86i24FPWQyS2q0R0Qe8-mdhMShlJF0RWQ0VKQ0G0009WRlTKji1jTk1i4s1k1W80GwHi000108jXMGV0RezMT2_WRdEVT0e8S3K9IEJfQKtbeT35kOpVO7AYKiG7W7Dk7um7f7F4S000WQ7kwgZ-07Vz_cHsm7OAE_GUu7VkPyPFB_ygRc0707O2E_GV87S24FOaU40wy1WLpzZ-H7gWU0T0Ue_lFcUMJozsP0TWU-jeUe1_hfy8Ui1y1o1_hwPbEqXy6DZOnCZWrsH_W7-WVy1y1W202Y20CgI2m882Ae0ZW80788G7G8V___m6m8W788W8c86441s8CCoJHZ7Me3YKw-GJUWBqpAKaSqM8awv0J148HKMt6nswLhfO8G337-z269z2m3eie7v_BXu-vV5VYv0cPO5YXEDljTQ3vOfFTZIlpNIMn_Aq4i7cx1-naIoVBmKvnGb7Z44UOIZBYmoI4tRQv70XLAuh3G_E9sXRY0G00~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyIxNTAyMjE2NjU2MjUwNjc5NzEiOiIyNDZ4MzAwIn0%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyIxNTAyMjE2NjU2MjUwNjc5NzEiOiI0MjQzNDczIn0%3D&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

РЕКЛАМА

[![](https://favicon.yandex.net/favicon/stepik.org?size=32&stub=2)

stepik.org



](https://yandex.ru/an/count/X1CejI_zOEm3JI00T3XDy-EryUyD0WK0x0GnfAyzOm00000uujL9wCknyzY8oAkQ0O01_hTmY07-jt2G0OR7ifBZyzYL1A01ji7MgTo0W802g06smTQfNB01qAJd1xW1siV3_IJ00GBO0TRJivm1u06QwAgK0UW12FW1vexUlW680WUW0jJAl1Qv0lZspq6fPtuEm0B-jt3m0io7jOSAq6Ie0nYg0VW4dvtl0OW5nzEw0P05dvtl0Q05Ylv8g0M8wJom1OZfFBW5YEaym0Nfh9q1o0N6W2ZG1UAa5U05jOSeapHK0DzjgGTzmr3ifabFKRW7mWlG1n3O1mg9me200k08ggMU2-W91sD4Qf81f_S_oGwg2n0FqMuYVSC00BOvNm5CwkWBnzEw0V0B2uWCvexUlW7e39y6c0sepYhW3OA0W860W808FuVHpAJ3Yi3lRQ0Em8Gz_OQ3xk-qqgTHW13hfy8Ua12_WvdagRsBeeB0i13G4DM6hr_u4AgSthqMu17iwvG7w17teAxq_hZlwWrWOq1X48EbRmRzF-aIdTopoQYoEt3m4WcJXxZgkT3IXXVW4uhTEO0KW82028WKrF3vZ-N3mPJc0Q0KYjqvg1JRX-C1i1JmtyWek1IWdR0C0j0Kw_MbRzWKi9_vc0RW507e58m2q1Mmd_cO1l0LmOhsxAEFlFnZe1RmligP1h0MemV95j0MvexUlW7O5e4Nc1U0vPuhg1S9k1S1m1UrbW7G5z260zWNzU8-w1S4e1W5i1Z1jVQP1hWODT0O8VWOfeVjZEwDhjBL0O0PiFIuuj2zaRaWYHbSdma000000A0PWWEm6RWPmD8P4dbXOdDVSsLoTcLoBt8tCZajC-0P1EWPxWNm6O320u4Q__ypptw1PT-86i24FPWQyS2q0R0Qe8-mdhMShlJF0RWQ0VKQ0G0009WRlTKji1jTk1i4s1k1W80GwHi000108jXMGV0RezMT2_WRdEVT0e8S3K9IEJfQKtbeT35kOpVO7AYKiG7W7Dk7um7f7F4S000WQ7kwgZ-07Vz_cHsm7OAE_GUu7VkPyPFB_ygRc0707O2E_GV87S24FOaU40wy1WLpzZ-H7gWU0T0Ue_lFcUMJozsP0TWU-jeUe1_hfy8Ui1y1o1_hwPbEqXy6DZOnCZWrsH_W7-WVy1y1W202Y20CgI2m882Ae0ZW80788G7G8V___m6m8W788W8c86441s8CCoJHZ7Me3YKw-GJUWBqpAKaSqM8awv0J148HKMt6nswLhfO8G337-z269z2m3eie7v_BXu-vV5VYv0cPO5YXEDljTQ3vOfFTZIlpNIMn_Aq4i7cx1-naIoVBmKvnGb7Z44UOIZBYmoI4tRQv70XLAuh3G_E9sXRY0G00~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyIxNTAyMjE2NjU2MjUwNjc5NzEiOiIyNDZ4MzAwIn0%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyIxNTAyMjE2NjU2MjUwNjc5NzEiOiI0MjQzNDczIn0%3D&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

[

Selenium Python. 970 ₽

](https://yandex.ru/an/count/X1CejI_zOEm3JI00T3XDy-EryUyD0WK0x0GnfAyzOm00000uujL9wCknyzY8oAkQ0O01_hTmY07-jt2G0OR7ifBZyzYL1A01ji7MgTo0W802g06smTQfNB01qAJd1xW1siV3_IJ00GBO0TRJivm1u06QwAgK0UW12FW1vexUlW680WUW0jJAl1Qv0lZspq6fPtuEm0B-jt3m0io7jOSAq6Ie0nYg0VW4dvtl0OW5nzEw0P05dvtl0Q05Ylv8g0M8wJom1OZfFBW5YEaym0Nfh9q1o0N6W2ZG1UAa5U05jOSeapHK0DzjgGTzmr3ifabFKRW7mWlG1n3O1mg9me200k08ggMU2-W91sD4Qf81f_S_oGwg2n0FqMuYVSC00BOvNm5CwkWBnzEw0V0B2uWCvexUlW7e39y6c0sepYhW3OA0W860W808FuVHpAJ3Yi3lRQ0Em8Gz_OQ3xk-qqgTHW13hfy8Ua12_WvdagRsBeeB0i13G4DM6hr_u4AgSthqMu17iwvG7w17teAxq_hZlwWrWOq1X48EbRmRzF-aIdTopoQYoEt3m4WcJXxZgkT3IXXVW4uhTEO0KW82028WKrF3vZ-N3mPJc0Q0KYjqvg1JRX-C1i1JmtyWek1IWdR0C0j0Kw_MbRzWKi9_vc0RW507e58m2q1Mmd_cO1l0LmOhsxAEFlFnZe1RmligP1h0MemV95j0MvexUlW7O5e4Nc1U0vPuhg1S9k1S1m1UrbW7G5z260zWNzU8-w1S4e1W5i1Z1jVQP1hWODT0O8VWOfeVjZEwDhjBL0O0PiFIuuj2zaRaWYHbSdma000000A0PWWEm6RWPmD8P4dbXOdDVSsLoTcLoBt8tCZajC-0P1EWPxWNm6O320u4Q__ypptw1PT-86i24FPWQyS2q0R0Qe8-mdhMShlJF0RWQ0VKQ0G0009WRlTKji1jTk1i4s1k1W80GwHi000108jXMGV0RezMT2_WRdEVT0e8S3K9IEJfQKtbeT35kOpVO7AYKiG7W7Dk7um7f7F4S000WQ7kwgZ-07Vz_cHsm7OAE_GUu7VkPyPFB_ygRc0707O2E_GV87S24FOaU40wy1WLpzZ-H7gWU0T0Ue_lFcUMJozsP0TWU-jeUe1_hfy8Ui1y1o1_hwPbEqXy6DZOnCZWrsH_W7-WVy1y1W202Y20CgI2m882Ae0ZW80788G7G8V___m6m8W788W8c86441s8CCoJHZ7Me3YKw-GJUWBqpAKaSqM8awv0J148HKMt6nswLhfO8G337-z269z2m3eie7v_BXu-vV5VYv0cPO5YXEDljTQ3vOfFTZIlpNIMn_Aq4i7cx1-naIoVBmKvnGb7Z44UOIZBYmoI4tRQv70XLAuh3G_E9sXRY0G00~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyIxNTAyMjE2NjU2MjUwNjc5NzEiOiIyNDZ4MzAwIn0%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyIxNTAyMjE2NjU2MjUwNjc5NzEiOiI0MjQzNDczIn0%3D&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

[Узнать больше](https://yandex.ru/an/count/X1CejI_zOEm3JI00T3XDy-EryUyD0WK0x0GnfAyzOm00000uujL9wCknyzY8oAkQ0O01_hTmY07-jt2G0OR7ifBZyzYL1A01ji7MgTo0W802g06smTQfNB01qAJd1xW1siV3_IJ00GBO0TRJivm1u06QwAgK0UW12FW1vexUlW680WUW0jJAl1Qv0lZspq6fPtuEm0B-jt3m0io7jOSAq6Ie0nYg0VW4dvtl0OW5nzEw0P05dvtl0Q05Ylv8g0M8wJom1OZfFBW5YEaym0Nfh9q1o0N6W2ZG1UAa5U05jOSeapHK0DzjgGTzmr3ifabFKRW7mWlG1n3O1mg9me200k08ggMU2-W91sD4Qf81f_S_oGwg2n0FqMuYVSC00BOvNm5CwkWBnzEw0V0B2uWCvexUlW7e39y6c0sepYhW3OA0W860W808FuVHpAJ3Yi3lRQ0Em8Gz_OQ3xk-qqgTHW13hfy8Ua12_WvdagRsBeeB0i13G4DM6hr_u4AgSthqMu17iwvG7w17teAxq_hZlwWrWOq1X48EbRmRzF-aIdTopoQYoEt3m4WcJXxZgkT3IXXVW4uhTEO0KW82028WKrF3vZ-N3mPJc0Q0KYjqvg1JRX-C1i1JmtyWek1IWdR0C0j0Kw_MbRzWKi9_vc0RW507e58m2q1Mmd_cO1l0LmOhsxAEFlFnZe1RmligP1h0MemV95j0MvexUlW7O5e4Nc1U0vPuhg1S9k1S1m1UrbW7G5z260zWNzU8-w1S4e1W5i1Z1jVQP1hWODT0O8VWOfeVjZEwDhjBL0O0PiFIuuj2zaRaWYHbSdma000000A0PWWEm6RWPmD8P4dbXOdDVSsLoTcLoBt8tCZajC-0P1EWPxWNm6O320u4Q__ypptw1PT-86i24FPWQyS2q0R0Qe8-mdhMShlJF0RWQ0VKQ0G0009WRlTKji1jTk1i4s1k1W80GwHi000108jXMGV0RezMT2_WRdEVT0e8S3K9IEJfQKtbeT35kOpVO7AYKiG7W7Dk7um7f7F4S000WQ7kwgZ-07Vz_cHsm7OAE_GUu7VkPyPFB_ygRc0707O2E_GV87S24FOaU40wy1WLpzZ-H7gWU0T0Ue_lFcUMJozsP0TWU-jeUe1_hfy8Ui1y1o1_hwPbEqXy6DZOnCZWrsH_W7-WVy1y1W202Y20CgI2m882Ae0ZW80788G7G8V___m6m8W788W8c86441s8CCoJHZ7Me3YKw-GJUWBqpAKaSqM8awv0J148HKMt6nswLhfO8G337-z269z2m3eie7v_BXu-vV5VYv0cPO5YXEDljTQ3vOfFTZIlpNIMn_Aq4i7cx1-naIoVBmKvnGb7Z44UOIZBYmoI4tRQv70XLAuh3G_E9sXRY0G00~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyIxNTAyMjE2NjU2MjUwNjc5NzEiOiIyNDZ4MzAwIn0%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyIxNTAyMjE2NjU2MjUwNjc5NzEiOiI0MjQzNDczIn0%3D&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

[

![](https://avatars.mds.yandex.net/get-direct/5146926/83JFSF0rv4U-cHocUDZJTw/wy150)





](https://yandex.ru/an/count/WymejI_zOB835Hu0f3DDy-ErxJS3b0K0iWGnfAyzOm00000uujL9XfFitvZMxPkV0O01dUJV0uW1m8VG3901_jkMkjA0W802c07-svQwKg01mAoe0S2ibhfIk07OsjNX8i010jW1v8UVdG7W0Uxib1Fe0Ixu0SYuthu1Y087e0A6jhK8kGBuziz1gMT-3l02p8UrXmhGPA031AW363Vu1EQlkWI81P_W_WEG1UQlkWIW1SY1hW6e1QU1aG6m1QU1aG6u1QU1aG6vu3A7A9CqL03VRQa7VSDGxAP9Jr6u1u05Y821mf201k08WzkQ1EW9003mFyaAFWSsdJqA0a0EgWiG3z5k8dt3002sELy1JEhe2v_W_WFm2mk839J8thu1gGn84Zpy3M3jF-WCdmQO3QZEAk0DWe20WO20W0YmFeVHpAJ3Yi3lRQ0Em8Gz_OQ3xk-qqgTHsGyOfNSrl043G80Gye7u7f0GluEPvAczYwA2-12gdDwz5k0HxEkK1-WHzw2kzFwux-eDyM1ZG5vjxgENY1L0wHATtBF9gB8xSF0I2PE7kEgvqDA65-0JcD690OWKrF3vZ-N3mPJc0Q0KcD690QWKewwT19tAwPS6u1G1w1IC0j0LdShfbmRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5fJ8thu1s1Q15vWNuidJ4wWN2RWN0S0NjPO1s1V0X3te5mAW60sm6C6rzfa6k1XMq1WX-1YcX-sCxeskqjK1W1cmzBZYqBsHkI296LoV2G000000e1c20x0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a2w1dk1V0PWC83WHh__nSfSP2QV8WQm8Gzc1hnmBG1e1hFZ9lcnCVCc3wm6g2Fi9wrdAxqpm6u6WFr6W40002O6xtLBR0RNRWR188S3K9IEJfQKtbeT35kOpUX70000C0F4go_gHm8mB4SgR-vGDWSyUBa0-0SewwT1EaSyHm0021eUxggFu0T_t-P7V0_o1t0X3s97f4Ug1u1q1xtyzkTaC2sw37O7lhQ7g0Vye7u7h0V0yWVyiFFJj8V1ZOsCJ8uDV0V0O0W0eWW3B0WX80Wu206q27___y1i281o282A21111w467FCkZ3M0RxIW344IoE7uI1Ho8asaNgOk8F_HlPuZwEtnRaReSuk1pXf1DXo649e3J_c3F9SHZpCxViGzrCEec4bOkFVZf3tdgjbN4y-ALg4fNdRmzT3AYp06EXHzyTOYmixSoh9Y12J49O8_tTZK4Vr5AX2YK8xc2CBkKHje_40~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyI3MjA1NzYwNTEwNDc4NTE1MSI6IjI0NngzMDAifQ%3D%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNTEwNDc4NTE1MSI6IjU3Mzk0In0%3D&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

РЕКЛАМА

[![](https://favicon.yandex.net/favicon/business.yandex.ru?size=32&stub=2)

business.yandex.ru



](https://yandex.ru/an/count/WymejI_zOB835Hu0f3DDy-ErxJS3b0K0iWGnfAyzOm00000uujL9XfFitvZMxPkV0O01dUJV0uW1m8VG3901_jkMkjA0W802c07-svQwKg01mAoe0S2ibhfIk07OsjNX8i010jW1v8UVdG7W0Uxib1Fe0Ixu0SYuthu1Y087e0A6jhK8kGBuziz1gMT-3l02p8UrXmhGPA031AW363Vu1EQlkWI81P_W_WEG1UQlkWIW1SY1hW6e1QU1aG6m1QU1aG6u1QU1aG6vu3A7A9CqL03VRQa7VSDGxAP9Jr6u1u05Y821mf201k08WzkQ1EW9003mFyaAFWSsdJqA0a0EgWiG3z5k8dt3002sELy1JEhe2v_W_WFm2mk839J8thu1gGn84Zpy3M3jF-WCdmQO3QZEAk0DWe20WO20W0YmFeVHpAJ3Yi3lRQ0Em8Gz_OQ3xk-qqgTHsGyOfNSrl043G80Gye7u7f0GluEPvAczYwA2-12gdDwz5k0HxEkK1-WHzw2kzFwux-eDyM1ZG5vjxgENY1L0wHATtBF9gB8xSF0I2PE7kEgvqDA65-0JcD690OWKrF3vZ-N3mPJc0Q0KcD690QWKewwT19tAwPS6u1G1w1IC0j0LdShfbmRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5fJ8thu1s1Q15vWNuidJ4wWN2RWN0S0NjPO1s1V0X3te5mAW60sm6C6rzfa6k1XMq1WX-1YcX-sCxeskqjK1W1cmzBZYqBsHkI296LoV2G000000e1c20x0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a2w1dk1V0PWC83WHh__nSfSP2QV8WQm8Gzc1hnmBG1e1hFZ9lcnCVCc3wm6g2Fi9wrdAxqpm6u6WFr6W40002O6xtLBR0RNRWR188S3K9IEJfQKtbeT35kOpUX70000C0F4go_gHm8mB4SgR-vGDWSyUBa0-0SewwT1EaSyHm0021eUxggFu0T_t-P7V0_o1t0X3s97f4Ug1u1q1xtyzkTaC2sw37O7lhQ7g0Vye7u7h0V0yWVyiFFJj8V1ZOsCJ8uDV0V0O0W0eWW3B0WX80Wu206q27___y1i281o282A21111w467FCkZ3M0RxIW344IoE7uI1Ho8asaNgOk8F_HlPuZwEtnRaReSuk1pXf1DXo649e3J_c3F9SHZpCxViGzrCEec4bOkFVZf3tdgjbN4y-ALg4fNdRmzT3AYp06EXHzyTOYmixSoh9Y12J49O8_tTZK4Vr5AX2YK8xc2CBkKHje_40~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyI3MjA1NzYwNTEwNDc4NTE1MSI6IjI0NngzMDAifQ%3D%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNTEwNDc4NTE1MSI6IjU3Mzk0In0%3D&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

[

Новые клиенты для химчистки

](https://yandex.ru/an/count/WymejI_zOB835Hu0f3DDy-ErxJS3b0K0iWGnfAyzOm00000uujL9XfFitvZMxPkV0O01dUJV0uW1m8VG3901_jkMkjA0W802c07-svQwKg01mAoe0S2ibhfIk07OsjNX8i010jW1v8UVdG7W0Uxib1Fe0Ixu0SYuthu1Y087e0A6jhK8kGBuziz1gMT-3l02p8UrXmhGPA031AW363Vu1EQlkWI81P_W_WEG1UQlkWIW1SY1hW6e1QU1aG6m1QU1aG6u1QU1aG6vu3A7A9CqL03VRQa7VSDGxAP9Jr6u1u05Y821mf201k08WzkQ1EW9003mFyaAFWSsdJqA0a0EgWiG3z5k8dt3002sELy1JEhe2v_W_WFm2mk839J8thu1gGn84Zpy3M3jF-WCdmQO3QZEAk0DWe20WO20W0YmFeVHpAJ3Yi3lRQ0Em8Gz_OQ3xk-qqgTHsGyOfNSrl043G80Gye7u7f0GluEPvAczYwA2-12gdDwz5k0HxEkK1-WHzw2kzFwux-eDyM1ZG5vjxgENY1L0wHATtBF9gB8xSF0I2PE7kEgvqDA65-0JcD690OWKrF3vZ-N3mPJc0Q0KcD690QWKewwT19tAwPS6u1G1w1IC0j0LdShfbmRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5fJ8thu1s1Q15vWNuidJ4wWN2RWN0S0NjPO1s1V0X3te5mAW60sm6C6rzfa6k1XMq1WX-1YcX-sCxeskqjK1W1cmzBZYqBsHkI296LoV2G000000e1c20x0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a2w1dk1V0PWC83WHh__nSfSP2QV8WQm8Gzc1hnmBG1e1hFZ9lcnCVCc3wm6g2Fi9wrdAxqpm6u6WFr6W40002O6xtLBR0RNRWR188S3K9IEJfQKtbeT35kOpUX70000C0F4go_gHm8mB4SgR-vGDWSyUBa0-0SewwT1EaSyHm0021eUxggFu0T_t-P7V0_o1t0X3s97f4Ug1u1q1xtyzkTaC2sw37O7lhQ7g0Vye7u7h0V0yWVyiFFJj8V1ZOsCJ8uDV0V0O0W0eWW3B0WX80Wu206q27___y1i281o282A21111w467FCkZ3M0RxIW344IoE7uI1Ho8asaNgOk8F_HlPuZwEtnRaReSuk1pXf1DXo649e3J_c3F9SHZpCxViGzrCEec4bOkFVZf3tdgjbN4y-ALg4fNdRmzT3AYp06EXHzyTOYmixSoh9Y12J49O8_tTZK4Vr5AX2YK8xc2CBkKHje_40~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyI3MjA1NzYwNTEwNDc4NTE1MSI6IjI0NngzMDAifQ%3D%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNTEwNDc4NTE1MSI6IjU3Mzk0In0%3D&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

[

Яндекс Биз­нес сам со­здаст и за­пу­стит ре­кламу для хим­чистки

](https://yandex.ru/an/count/WymejI_zOB835Hu0f3DDy-ErxJS3b0K0iWGnfAyzOm00000uujL9XfFitvZMxPkV0O01dUJV0uW1m8VG3901_jkMkjA0W802c07-svQwKg01mAoe0S2ibhfIk07OsjNX8i010jW1v8UVdG7W0Uxib1Fe0Ixu0SYuthu1Y087e0A6jhK8kGBuziz1gMT-3l02p8UrXmhGPA031AW363Vu1EQlkWI81P_W_WEG1UQlkWIW1SY1hW6e1QU1aG6m1QU1aG6u1QU1aG6vu3A7A9CqL03VRQa7VSDGxAP9Jr6u1u05Y821mf201k08WzkQ1EW9003mFyaAFWSsdJqA0a0EgWiG3z5k8dt3002sELy1JEhe2v_W_WFm2mk839J8thu1gGn84Zpy3M3jF-WCdmQO3QZEAk0DWe20WO20W0YmFeVHpAJ3Yi3lRQ0Em8Gz_OQ3xk-qqgTHsGyOfNSrl043G80Gye7u7f0GluEPvAczYwA2-12gdDwz5k0HxEkK1-WHzw2kzFwux-eDyM1ZG5vjxgENY1L0wHATtBF9gB8xSF0I2PE7kEgvqDA65-0JcD690OWKrF3vZ-N3mPJc0Q0KcD690QWKewwT19tAwPS6u1G1w1IC0j0LdShfbmRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5fJ8thu1s1Q15vWNuidJ4wWN2RWN0S0NjPO1s1V0X3te5mAW60sm6C6rzfa6k1XMq1WX-1YcX-sCxeskqjK1W1cmzBZYqBsHkI296LoV2G000000e1c20x0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a2w1dk1V0PWC83WHh__nSfSP2QV8WQm8Gzc1hnmBG1e1hFZ9lcnCVCc3wm6g2Fi9wrdAxqpm6u6WFr6W40002O6xtLBR0RNRWR188S3K9IEJfQKtbeT35kOpUX70000C0F4go_gHm8mB4SgR-vGDWSyUBa0-0SewwT1EaSyHm0021eUxggFu0T_t-P7V0_o1t0X3s97f4Ug1u1q1xtyzkTaC2sw37O7lhQ7g0Vye7u7h0V0yWVyiFFJj8V1ZOsCJ8uDV0V0O0W0eWW3B0WX80Wu206q27___y1i281o282A21111w467FCkZ3M0RxIW344IoE7uI1Ho8asaNgOk8F_HlPuZwEtnRaReSuk1pXf1DXo649e3J_c3F9SHZpCxViGzrCEec4bOkFVZf3tdgjbN4y-ALg4fNdRmzT3AYp06EXHzyTOYmixSoh9Y12J49O8_tTZK4Vr5AX2YK8xc2CBkKHje_40~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyI3MjA1NzYwNTEwNDc4NTE1MSI6IjI0NngzMDAifQ%3D%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNTEwNDc4NTE1MSI6IjU3Mzk0In0%3D&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

[Узнать больше](https://yandex.ru/an/count/WymejI_zOB835Hu0f3DDy-ErxJS3b0K0iWGnfAyzOm00000uujL9XfFitvZMxPkV0O01dUJV0uW1m8VG3901_jkMkjA0W802c07-svQwKg01mAoe0S2ibhfIk07OsjNX8i010jW1v8UVdG7W0Uxib1Fe0Ixu0SYuthu1Y087e0A6jhK8kGBuziz1gMT-3l02p8UrXmhGPA031AW363Vu1EQlkWI81P_W_WEG1UQlkWIW1SY1hW6e1QU1aG6m1QU1aG6u1QU1aG6vu3A7A9CqL03VRQa7VSDGxAP9Jr6u1u05Y821mf201k08WzkQ1EW9003mFyaAFWSsdJqA0a0EgWiG3z5k8dt3002sELy1JEhe2v_W_WFm2mk839J8thu1gGn84Zpy3M3jF-WCdmQO3QZEAk0DWe20WO20W0YmFeVHpAJ3Yi3lRQ0Em8Gz_OQ3xk-qqgTHsGyOfNSrl043G80Gye7u7f0GluEPvAczYwA2-12gdDwz5k0HxEkK1-WHzw2kzFwux-eDyM1ZG5vjxgENY1L0wHATtBF9gB8xSF0I2PE7kEgvqDA65-0JcD690OWKrF3vZ-N3mPJc0Q0KcD690QWKewwT19tAwPS6u1G1w1IC0j0LdShfbmRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5fJ8thu1s1Q15vWNuidJ4wWN2RWN0S0NjPO1s1V0X3te5mAW60sm6C6rzfa6k1XMq1WX-1YcX-sCxeskqjK1W1cmzBZYqBsHkI296LoV2G000000e1c20x0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a2w1dk1V0PWC83WHh__nSfSP2QV8WQm8Gzc1hnmBG1e1hFZ9lcnCVCc3wm6g2Fi9wrdAxqpm6u6WFr6W40002O6xtLBR0RNRWR188S3K9IEJfQKtbeT35kOpUX70000C0F4go_gHm8mB4SgR-vGDWSyUBa0-0SewwT1EaSyHm0021eUxggFu0T_t-P7V0_o1t0X3s97f4Ug1u1q1xtyzkTaC2sw37O7lhQ7g0Vye7u7h0V0yWVyiFFJj8V1ZOsCJ8uDV0V0O0W0eWW3B0WX80Wu206q27___y1i281o282A21111w467FCkZ3M0RxIW344IoE7uI1Ho8asaNgOk8F_HlPuZwEtnRaReSuk1pXf1DXo649e3J_c3F9SHZpCxViGzrCEec4bOkFVZf3tdgjbN4y-ALg4fNdRmzT3AYp06EXHzyTOYmixSoh9Y12J49O8_tTZK4Vr5AX2YK8xc2CBkKHje_40~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyI3MjA1NzYwNTEwNDc4NTE1MSI6IjI0NngzMDAifQ%3D%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNTEwNDc4NTE1MSI6IjU3Mzk0In0%3D&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

[](https://practicum.yandex.ru/backend-developer/?utm_source=yandex&utm_medium=cpc&utm_campaign=Yan_Net_RF_Pyth_Kursy-exp-tgo1-4_460&utm_content=sty_context%3As_pythonchik.ru%3Acid_66390989%3Agid_4717091926%3Apid_34411505154%3Aaid_12438186354%3Acrid_0%3Arid_%3Ap_0%3Apty_none%3Amty_%3Amkw_%3Adty_desktop%3Acgcid_0%3Arn_%D0%92%D0%BE%D1%80%D0%BE%D0%BD%D0%B5%D0%B6%3Arid_193&utm_term=%D0%BF%D0%B8%D1%82%D0%BE%D0%BD%20%D1%83%D1%87%D0%B8%D1%82%D1%8C&_openstat=ZGlyZWN0LnlhbmRleC5ydTs2NjM5MDk4OTsxMjQzODE4NjM1NDtweXRob25jaGlrLnJ1Omd1YXJhbnRlZQ&yclid=14806158974788042751&stat-id=7&test-tag=442553430235697&banner-sizes=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjI0NngzMDAifQ%3D%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjcxMjcyMyJ9&order-banners-options=eyI3MjA1NzYwNjQ3NjExNDM5OCI6MjA0OH0&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300#short-program)

РЕКЛАМА

[![](https://favicon.yandex.net/favicon/practicum.yandex.ru?size=32&stub=2)

practicum.yandex.ru



](https://yandex.ru/an/count/X1eejI_zOFG3XI0013bDy-ErMV52PmK0z0GnfAyzOm00000uujL9XfFitvZMxPkV0O01Zl3od0M80OBCrvY00P01lAVzrTo0W802c06yf_tLNA01vAMe0UIb_TLSk06iySYI8y010jW1chFNdW7W0SBEfPK1w04a-07cZjw-0OW21w02fflb6Ba2-FRFGQbdVWxm0io7jOSAq6IO0y24FQ031gW368m1-0J_xCi1Y0Nxfh41a0N_xCi1e0NAc3we1UZfCx05wEapk0NewJF01P78ZWF81PggPT05wf4Iu0KlXoYJD5G0tssf1tt3KEocIKzHk0Uq1WRG2Bg8W872W806u0ZJpR8Cw0a9Q_vDI4lWFyaA0F0_3geB40_HRY9zmm00jZbV0Kpgw0lxfh41y0iBY0pczzw-0UWCdmQO3QZEAk0DWe20WO20W0XmFOVHpAJ3Yi3lRQ0Ehlaw_OQ3xk-qqgTHW13DbzGVa12_WvdagRsBeeB0i13u4AgSthqMu17iwvG7w17teAxq_hZlwWrWOq15pHEUWhO2GEaIdTopoQYoEt3m4WcJXxZgkT3IXXVW4xAOCO0KWA02Y1JKyFcFvSF1bEO1e1Ioc36e5EUzmG6m58lyoJEu5C2KtW_05830qU4Zo1G2q1JfflWLs1IYbuoP1k0K0UWKZ0B85TZC-8Ez1D0L_OkicGRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5kRtthu1s1Q15vWNX9x7AwWN2RWN0S0NjPO1q1VGXWFO5xQdFUWN0w0O5B0OmRNscGQu60NG627u6AQ7xOpkZQxIrG606R3qkEBGlP6v88aPN9y90000002W6O83g1cg-lYL1B0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a2w1dk1V0PWC83-1cde8KTWHh__pCa90jwpOWQm8Gzc1hnmBG1i1gWZx2UjPokzCy1k1e3zHe10000c1kzrIsm6rsu6mJf6m00043plA51y1kFaegN0lWRezgNPO8S3K9IEJfQKtbeT35kOpVO7D2ag07W7EUzmG7f7F4S000WQ7kwgZ-07Vz_cHt87S24FU0TgwW7YHxxBstZEExUFv4Ug1u1q1xedul_dj6rg8G1s1xwsXw87____m6W7ysNr1-m7mJ87ytPgq_I7mOsDZ4oE3NP7-0Vw1_m7m6080A880of8B0WX80Wu206q27__m608a2m8W788W8d8844YJ546P9iGWzNCtg1F0B7nTQOE4X7OvqqaOJib5C4uubeDrlmRjomIWGdsCFxv0ubZCVYik5hxjwBE7XO9XPMAhvx6nryljlaUUHA6K-J9ay70O2UwQ7sPbER9GF4B7GiFACg_OWJqn1stnWub5KeFyHZvFDQrb7RGZm0~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjI0NngzMDAifQ%3D%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjcxMjcyMyJ9&order-banners-options=eyI3MjA1NzYwNjQ3NjExNDM5OCI6MjA0OH0&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

[

Программирование на Python — курс от Яндекса

](https://yandex.ru/an/count/X1eejI_zOFG3XI0013bDy-ErMV52PmK0z0GnfAyzOm00000uujL9XfFitvZMxPkV0O01Zl3od0M80OBCrvY00P01lAVzrTo0W802c06yf_tLNA01vAMe0UIb_TLSk06iySYI8y010jW1chFNdW7W0SBEfPK1w04a-07cZjw-0OW21w02fflb6Ba2-FRFGQbdVWxm0io7jOSAq6IO0y24FQ031gW368m1-0J_xCi1Y0Nxfh41a0N_xCi1e0NAc3we1UZfCx05wEapk0NewJF01P78ZWF81PggPT05wf4Iu0KlXoYJD5G0tssf1tt3KEocIKzHk0Uq1WRG2Bg8W872W806u0ZJpR8Cw0a9Q_vDI4lWFyaA0F0_3geB40_HRY9zmm00jZbV0Kpgw0lxfh41y0iBY0pczzw-0UWCdmQO3QZEAk0DWe20WO20W0XmFOVHpAJ3Yi3lRQ0Ehlaw_OQ3xk-qqgTHW13DbzGVa12_WvdagRsBeeB0i13u4AgSthqMu17iwvG7w17teAxq_hZlwWrWOq15pHEUWhO2GEaIdTopoQYoEt3m4WcJXxZgkT3IXXVW4xAOCO0KWA02Y1JKyFcFvSF1bEO1e1Ioc36e5EUzmG6m58lyoJEu5C2KtW_05830qU4Zo1G2q1JfflWLs1IYbuoP1k0K0UWKZ0B85TZC-8Ez1D0L_OkicGRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5kRtthu1s1Q15vWNX9x7AwWN2RWN0S0NjPO1q1VGXWFO5xQdFUWN0w0O5B0OmRNscGQu60NG627u6AQ7xOpkZQxIrG606R3qkEBGlP6v88aPN9y90000002W6O83g1cg-lYL1B0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a2w1dk1V0PWC83-1cde8KTWHh__pCa90jwpOWQm8Gzc1hnmBG1i1gWZx2UjPokzCy1k1e3zHe10000c1kzrIsm6rsu6mJf6m00043plA51y1kFaegN0lWRezgNPO8S3K9IEJfQKtbeT35kOpVO7D2ag07W7EUzmG7f7F4S000WQ7kwgZ-07Vz_cHt87S24FU0TgwW7YHxxBstZEExUFv4Ug1u1q1xedul_dj6rg8G1s1xwsXw87____m6W7ysNr1-m7mJ87ytPgq_I7mOsDZ4oE3NP7-0Vw1_m7m6080A880of8B0WX80Wu206q27__m608a2m8W788W8d8844YJ546P9iGWzNCtg1F0B7nTQOE4X7OvqqaOJib5C4uubeDrlmRjomIWGdsCFxv0ubZCVYik5hxjwBE7XO9XPMAhvx6nryljlaUUHA6K-J9ay70O2UwQ7sPbER9GF4B7GiFACg_OWJqn1stnWub5KeFyHZvFDQrb7RGZm0~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjI0NngzMDAifQ%3D%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjcxMjcyMyJ9&order-banners-options=eyI3MjA1NzYwNjQ3NjExNDM5OCI6MjA0OH0&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

[Узнать больше](https://yandex.ru/an/count/X1eejI_zOFG3XI0013bDy-ErMV52PmK0z0GnfAyzOm00000uujL9XfFitvZMxPkV0O01Zl3od0M80OBCrvY00P01lAVzrTo0W802c06yf_tLNA01vAMe0UIb_TLSk06iySYI8y010jW1chFNdW7W0SBEfPK1w04a-07cZjw-0OW21w02fflb6Ba2-FRFGQbdVWxm0io7jOSAq6IO0y24FQ031gW368m1-0J_xCi1Y0Nxfh41a0N_xCi1e0NAc3we1UZfCx05wEapk0NewJF01P78ZWF81PggPT05wf4Iu0KlXoYJD5G0tssf1tt3KEocIKzHk0Uq1WRG2Bg8W872W806u0ZJpR8Cw0a9Q_vDI4lWFyaA0F0_3geB40_HRY9zmm00jZbV0Kpgw0lxfh41y0iBY0pczzw-0UWCdmQO3QZEAk0DWe20WO20W0XmFOVHpAJ3Yi3lRQ0Ehlaw_OQ3xk-qqgTHW13DbzGVa12_WvdagRsBeeB0i13u4AgSthqMu17iwvG7w17teAxq_hZlwWrWOq15pHEUWhO2GEaIdTopoQYoEt3m4WcJXxZgkT3IXXVW4xAOCO0KWA02Y1JKyFcFvSF1bEO1e1Ioc36e5EUzmG6m58lyoJEu5C2KtW_05830qU4Zo1G2q1JfflWLs1IYbuoP1k0K0UWKZ0B85TZC-8Ez1D0L_OkicGRm5S6AzkoZZxpyOw0MyBxAcGQm5gC7oHRG5kRtthu1s1Q15vWNX9x7AwWN2RWN0S0NjPO1q1VGXWFO5xQdFUWN0w0O5B0OmRNscGQu60NG627u6AQ7xOpkZQxIrG606R3qkEBGlP6v88aPN9y90000002W6O83g1cg-lYL1B0Pk1d0qXaIUM5YSrzpPN9sPN8lSZSoEIqpu1a2w1dk1V0PWC83-1cde8KTWHh__pCa90jwpOWQm8Gzc1hnmBG1i1gWZx2UjPokzCy1k1e3zHe10000c1kzrIsm6rsu6mJf6m00043plA51y1kFaegN0lWRezgNPO8S3K9IEJfQKtbeT35kOpVO7D2ag07W7EUzmG7f7F4S000WQ7kwgZ-07Vz_cHt87S24FU0TgwW7YHxxBstZEExUFv4Ug1u1q1xedul_dj6rg8G1s1xwsXw87____m6W7ysNr1-m7mJ87ytPgq_I7mOsDZ4oE3NP7-0Vw1_m7m6080A880of8B0WX80Wu206q27__m608a2m8W788W8d8844YJ546P9iGWzNCtg1F0B7nTQOE4X7OvqqaOJib5C4uubeDrlmRjomIWGdsCFxv0ubZCVYik5hxjwBE7XO9XPMAhvx6nryljlaUUHA6K-J9ay70O2UwQ7sPbER9GF4B7GiFACg_OWJqn1stnWub5KeFyHZvFDQrb7RGZm0~1?stat-id=7&test-tag=442553430235697&banner-sizes=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjI0NngzMDAifQ%3D%3D&format-type=118&actual-format=14&pcodever=661285&banner-test-tags=eyI3MjA1NzYwNjQ3NjExNDM5OCI6IjcxMjcyMyJ9&order-banners-options=eyI3MjA1NzYwNjQ3NjExNDM5OCI6MjA0OH0&pcode-active-testids=652287%2C0%2C26%3B661140%2C0%2C96%3B651043%2C0%2C97&width=750&height=300)

Распаковка особенно удобна, когда функция возвращает несколько значений в виде кортежа (tuple):

```python
>>> def test_page():
	return 404, "Not found"

>>> code, message = test_page()
>>> print(code, message)
404 Not found
```

Главное условие распаковки – количество элементов должно совпадать

Если необходимо распаковать лишь несколько элементов, воспользуйтесь переменной со знаком "*":

```python
>>> text = "deactivate"
>>> first, second, *other_letters = text
>>> print(first, second, other_letters)
d e ['a', 'c', 't', 'i', 'v', 'a', 't', 'e']
```

## Побитовые операторы[](https://pythonchik.ru/osnovy/operatory-i-vyrazheniya-v-python#pobitovye-operatory)

Данные операторы предназначены для работы с данными в битовом (двоичном) формате. Про битовые операции смотрите [статью на википедии](https://ru.wikipedia.org/wiki/%D0%91%D0%B8%D1%82%D0%BE%D0%B2%D1%8B%D0%B5_%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D0%B8).

-   `~` — побитовое отрицание (для него требуется только один операнд);
-   `&` — побитовое "И";
-   `|` — побитовое "ИЛИ";
-   `^` — исключающее "ИЛИ";
-   `<<` — побитовый сдвиг влево;
-   `>>` — побитовый сдвиг вправо.

![Пример побитовых операций в Python.](https://pythonchik.ru/pic/lb1/intext_d516921e-24de-4ec5-a7c2-0141d077444a_original.svg)

Пример побитовых операций в Python.

```python
>>> a = 11
>>> b = 34

>>> a & b
2
>>> a | b
43
>>> (a ^ b)
41
>>> ~a
-12
>>> a << 1
22
>>> a >> 2
5
```

## Операторы членства[](https://pythonchik.ru/osnovy/operatory-i-vyrazheniya-v-python#operatory-chlenstva)

В Python существует всего 2 оператора принадлежности — `in` и `not in` и предназначены они для проверки наличия элемента в строке (str), списке (list), словаре (dict) или кортеже (tuple).

-   `in` — возвращает True если элемент присутствует в последовательности;
-   `not in` — возвращает True если элемент отсутствует в последовательности.

```python
>>> "host" in "host=local"
True
>>> 2 in [1,2,4,5]
True
>>> "one" in {"one": 1, "two": 1}  # в словаре проверка по ключам
True
>>> True in ("string", 2, True)
True
>>> "str" not in ("string", 2, True)
True
```

## Операторы тождественности[](https://pythonchik.ru/osnovy/operatory-i-vyrazheniya-v-python#operatory-tozhdestvennosti)

Данные операторы сравнивают размещение двух объектов в памяти.

-   `is` — возвращает True если оба операнда указывают на один и тот же объект;
-   `is not` — возвращает True если оба операнда указывают на разные объекты.

```python
>>> x = 5
>>> type(x) is int
True

>>> x = 5.1
>>> type(x) is int
False

>>> x = [1, 2, 3]  # id(x) = 64620552
>>> y = [1, 2, 3]  # id(y) = 60529960
>>> x is y
False
```

## Приоритет операторов[](https://pythonchik.ru/osnovy/operatory-i-vyrazheniya-v-python#prioritet-operatorov)

Таблица приоритетов операторов в Python показана ниже.

![Таблица приоритетов выполнения операторов в Python.](https://pythonchik.ru/pic/lb1/intext_05f82c7c-1f87-4756-ab16-b972016e8e94_original.svg)

Таблица приоритетов выполнения операторов в Python.

Элементы отсортированы по убыванию, с высокого приоритета к более низкому. В комбинациях с несколькими операторами, оператор с большим приоритетом выполняется первым.

Например, в выражении `1 + 2 ** 2 * 10` сначала выполнится возведение в степень, далее умножение, потом сложение. Итого результат: `41`.