Pattern: Line is too long

Issue: -

## Description
Your source code should not contain very long lines. The default wrapping in most tools disrupts the visual structure of the code, making it more difficult to understand. Use the `\` character at the end of a line to tell the Python interpreter that the statement continues on the next line. Here is an example of how to break up a long boolean expression into three lines.


```python
  if ( ((blah < 0 ) and (grr > 234)) \ 
       or ((foo == 3456) and (grr <= 4444)) \
       or ((blah > 10) and (grr == 3333))  \
      ): 
    print "this crazy condition is true"    	
    print "and my code is really easy to read because"
    print "I didn't wrap lines!"

  else:
    print "this crazy condition is false"    	
```

By default this value is set to 159, although _PEP 8_ recommends a more strict range of 79 - 99 characters per line. In any case, you can set `max-line-length` in Pylint configuration file depending on your needs.

## Further Reading

* [PEP 8 - Maximum Line Length ](https://www.python.org/dev/peps/pep-0008/#maximum-line-length)
