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

Strings
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

>>> help(int)

Help on class int in module builtins:

class int(object)
 |  int([x]) -> integer
 |  int(x, base=10) -> integer
 |  
 |  Convert a number or string to an integer, or return 0 if no arguments
 |  are given.
...

>>> int('0XD903', 16)
55555
>>> int('D903', 16)
55555
```
More helps
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

# Pip and Virtualenv

**pip** is a tool for installing Python packages.

**virtualenv** is a tool to create isolated Python environments. virtualenv creates a folder which contains all the necessary executables to use the packages that a Python project would need.

Let's install virtualenv. Use sudo for Linux and MacOS, or run Windows Power Shell as Administrator
```bash
pip3 --version
pip3 install virtualenv

virtualenv --version

virtualenv --help

mkdir sandbox && cd sandbox
virtualenv -p python3 env3
source env3/bin/activate
# or .\Scripts\activate for Windows

➜  sandbox source env3/bin/activate
(env3) ➜  sandbox 
```

Install ptpython using virtualenv
```bash
(env3) ➜  sandbox python --version
Python 3.7.0
(env3) ➜  sandbox pip --version
pip 19.2.3 from /Users/vensder/sandbox/env3/lib/python3.7/site-packages/pip (python 3.7)
(env3) ➜  sandbox pip install ptpython
...
(env3) ➜  sandbox ptpython

>>> s = 'python-intro'

>>> s.
    capitalize        endswith          index             isidentifier      istitle           lstrip             
    casefold          expandtabs        isalnum           islower           isupper           maketrans          
    center            find              isalpha           isnumeric         join              partition         >
    count             format            isdecimal         isprintable       ljust             replace            
    encode            format_map        isdigit           isspace           lower             rfind              

```


Modules

```python
>>> import math

>>> math.pi
3.141592653589793

>>> import os

>>> os.cpu_count()
4

>>> 
```

## Simple Web Framework Bottle

Bottle is a fast, simple and lightweight WSGI micro web-framework for Python.

Run in virtual environment
```bash
pip install bottle
Collecting bottle
  Using cached https://files.pythonhosted.org/packages/69/d1/efdd0a5584169cdf791d726264089ce5d96846a8978c44ac6e13ae234327/bottle-0.12.17-py3-none-any.whl
Installing collected packages: bottle
Successfully installed bottle-0.12.17
```

```vim my_server.py # or any your's favorite editor```

```python
#!/usr/bin/env python3

from bottle import route, run
from bottle import template
import os

@route('/hello')
def hello():
    return "Hello World!"
```

```python
@route('/hello/<name>')
def greet(name='Stranger'):
    return template('Hello {{name}}, how are you?', name=name)
```

Some crazy stuff. Never do it in production, only for tests.
```python
@route('/my_eval')
@route('/my_eval/<my_string>')
def my_eval(my_string='2+2'):
    return my_string + '=' + str(eval(my_string))

run(host='localhost', port=8080, debug=True)
```

```
http://localhost:8080/my_eval/os.environ

http://localhost:8080/my_eval/dir(os)

http://localhost:8080/my_eval/os.cpu_count()

http://localhost:8080/my_eval/55%0

http://localhost:8080/my_eval/55%4

http://localhost:8080/my_eval/%22adsfa%22*3

http://localhost:8080/my_eval/3**3**3

http://localhost:8080/my_eval/4+5

http://localhost:8080/my_eval
```
