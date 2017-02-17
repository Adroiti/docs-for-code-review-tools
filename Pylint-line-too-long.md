Pattern: Line too long

Issue: -

## Description
Your source code should not contain lines that are longer than `max-line-length` characters long. If you have a line that is longer than `max-line-length` characters long, break it up into multiple lines. Use the `\` character at the end of a line to tell the Python interpreter that the statement continues on the next line. Here is an example of how to break up a long boolean expression into three lines.
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
By default `max-line-length` is 80 characters per line, but we are very liberal so we made it 150 characters per line just for you.

## Further Reading
* [Pylint - C0301](http://pylint-messages.wikidot.com/messages:c0301)
