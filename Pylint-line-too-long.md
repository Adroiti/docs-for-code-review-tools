Pattern: Line too long

Issue: -

## Description
Your source code should not contain very long lines. If you have lines that are very long you should break it up into multiple lines, because when code is not clearly visible it's very difficult to understand what it does. Use the `\` character at the end of a line to tell the Python interpreter that the statement continues on the next line. Here is an example of how to break up a long boolean expression into three lines.
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
By default PEP 8 recommends 79 - 99 characters per line, but we are very liberal so we made it 159 characters per line just for you.
You can set `max-line-length` in Pylint configuration file depending on your needs.

## Further Reading
* [Pylint - C0301](http://pylint-messages.wikidot.com/messages:c0301)
