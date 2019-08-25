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

```python
>>> hex
<built-in function hex>
>>> help(hex)

>>> hex(55555)
'0xd903'

>>> hex(55555).upper()
'0XD903'

>>> hex(55555).upper()[2:]
'D903'
```

