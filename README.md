# 'python-intro'.replace('-', ' ').title()

Just a simple Python intro for beginners

Check the python3 version
```bash
python3 --version
```

## REPL handy tools (python built-in functions)

REPL - A read–eval–print loop, also termed an interactive toplevel or language shell.

Run Python REPL
```bash
python3
Python 3.7.0 (v3.7.0:1bf9cc5093, Jun 26 2018, 23:26:24) 
[Clang 6.0 (clang-600.0.57)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> print('Hello Team H!')
Hello Team H!
```

Strings and numbers
```python
>>> s = 'python-intro'

>>> s.capitalize()
'Python-intro'

>>> s.title()
'Python-Intro'

>>> s.replace('-', ' ')
'python intro'

>>> s.replace('-', ' ').title()
'Python Intro'
```
Little help
```python
>>> hex
<built-in function hex>
>>> help(hex)

hex(number, /)
    Return the hexadecimal representation of an integer.
    
    >>> hex(12648430)
    '0xc0ffee'
(END)

>>> hex(55555)
'0xd903'

>>> hex(55555).upper()
'0XD903'

>>> hex(55555).upper()[2:]
'D903'

>>> int('0XD903', 16)
55555
>>> int('D903', 16)
55555
```

```python
# What can I upply for strings?
>>> dir(str)
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']


>>> for i in dir(str):
...   if '__' not in i:
...     print(i)
... 
capitalize
casefold
center
count
encode
endswith
expandtabs
find
format
format_map
index
isalnum
isalpha
isascii
isdecimal
isdigit
isidentifier
islower
isnumeric
isprintable
isspace
istitle
isupper
join
ljust
lower
lstrip
maketrans
partition
replace
rfind
rindex
rjust
rpartition
rsplit
rstrip
split
splitlines
startswith
strip
swapcase
title
translate
upper
zfill

>>> help(''.title)
Help on built-in function title:

title() method of builtins.str instance
    Return a version of the string where each word is titlecased.
    
    More specifically, words start with uppercased characters and all remaining
    cased characters have lower case.
(END)

```
