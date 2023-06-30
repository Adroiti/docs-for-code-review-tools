Pattern: Use of mutable default argument

Issue: -

## Description

Used when a mutable value as list or dictionary is detected in a default value for an argument. 


Usually when a programmer uses a list or dictionary as the default argument to a function, the programmer wants the program to create a new list or dictionary every time that the function is called. However, the first time that the function is called, Python creates a persistent object for the list or dictionary. Every subsequent time the function is called, Python uses that same persistent object that was created from the first call to the function.


Example of **incorrect** code:

```python
def foo(x=[]):
        x.append(1)
        print x
    ...
```

Example of **correct** code:

```python
def foo(x=None): # the keyword None is sentinel value representing empty list
    if x is None:
         x = []
    x.append(1) 
    print x
    ...
```

## Further Reading

* [Stack Overflow - Hidden Features of Python](http://stackoverflow.com/questions/101268/hidden-features-of-python#113198)
