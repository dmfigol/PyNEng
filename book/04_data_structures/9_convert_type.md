## Преобразование типов

В Python есть несколько полезных встроенных функций, которые позволяют преобразовать данные из одного типа в другой.

###```int()```

```int()``` - преобразует строку в int:
```python
In [1]: int("10")
Out[1]: 10
```

С помощью функции int можно преобразовать и число в двоичной записи в десятичную (двоичная запись должна быть в виде строки) 
```python
In [2]: int("11111111", 2)
Out[2]: 255
```

###```bin()```

Преобразовать десятичное число в двоичный формат можно с помощью ```bin()```:
```python
In [3]: bin(10)
Out[3]: '0b1010'

In [4]: bin(255)
Out[4]: '0b11111111'
```

###```hex()```

Аналогичная функция есть и для преобразования в шестнадцатеричный формат:
```python
In [5]: hex(10)
Out[5]: '0xa'

In [6]: hex(255)
Out[6]: '0xff'
```


###```list()```

Функция ```list()``` преобразует аргумент в список: 
```python
In [7]: list("string")
Out[7]: ['s', 't', 'r', 'i', 'n', 'g']

In [8]: list({1,2,3})
Out[8]: [1, 2, 3]

In [9]: list((1,2,3,4))
Out[9]: [1, 2, 3, 4]
```

###```set()```

Функция ```set()``` преобразует аргумент в множество: 
```python
In [10]: set([1,2,3,3,4,4,4,4])
Out[10]: {1, 2, 3, 4}

In [11]: set((1,2,3,3,4,4,4,4))
Out[11]: {1, 2, 3, 4}

In [12]: set("string string")
Out[12]: {' ', 'g', 'i', 'n', 'r', 's', 't'}
```

Эта функция очень полезна, когда нужно получить уникальные элементы в последовательности.

###```tuple()```

Функция ```tuple()``` преобразует аргумент в кортеж: 
```python
In [13]: tuple([1,2,3,4])
Out[13]: (1, 2, 3, 4)

In [14]: tuple({1,2,3,4})
Out[14]: (1, 2, 3, 4)

In [15]: tuple("string")
Out[15]: ('s', 't', 'r', 'i', 'n', 'g')
```

Это может пригодиться в том случае, если нужно получить неизменяемый объект.

###```str()```

Функция ```str()``` преобразует аргумент в строку: 
```python
In [16]: str(10)
Out[16]: '10'
```

Например, она пригодится в ситуации, когда есть список VLANов, который надо преобразовать в одну строку, где номера перечислены через запятую.

Если сделать ```join``` для списка чисел, возникнет ошибка:
```python
In [17]: vlans = [10, 20, 30, 40]

In [18]: ','.join(vlans)
------------------------------------------------------
TypeError           Traceback (most recent call last)
<ipython-input-39-d705aed3f1b3> in <module>()
----> 1 ','.join(vlans)

TypeError: sequence item 0: expected string, int found
```

Чтобы исправить это, нужно преобразовать числа в строки. Это удобно делать с помощью list comprehensions:
```python
In [19]: ','.join([ str(vlan) for vlan in vlans ])
Out[19]: '10,20,30,40'
```
