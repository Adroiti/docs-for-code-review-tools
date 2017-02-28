Pattern: Global statement

Issue: -

## Description

Global variables reduce code readability and often cause bugs. Avoid global variable as much as possible. 


Example of **incorrect** code:
```python
WIDTH = 0 # global variable

def area(w):
    global WIDTH # global statement
    WIDTH = w
    return WIDTH * WIDTH
```

One common solution for this is to create a class and to encapsulate global variables as members of an instantiated object of that class:


```python
class Square:
    def __init__(self, width):
        self.width = width
    def area(self):
        return self.width * self.width
```

## Further Reading

* [Wiki Wiki Web - Global Variables Are Bad](http://wiki.c2.com/?GlobalVariablesAreBad)
