Pattern: Line too long

Issue: -

## Description
Your source code should not contain lines that are longer than 80 characters long. If you have a line that is longer than 80 character, break it up into multiple lines. Use the '\' character at the end of a line to tell the Python interpreter that the statment continues on the next line: Here is an example of how to break up a long boolean expression into three lines:
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
The easiest way to make sure you are not adding lines longer than 80 characters wide is to always work inside a window that is exactly 80 characters wide. If your line starts wrapping around to the next line, its too long.

## Further Reading

* [Pylint - C0301](http://pylint-messages.wikidot.com/messages:c0301)