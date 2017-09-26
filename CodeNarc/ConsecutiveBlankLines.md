Pattern: Consecutive blank lines

Issue: -

## Description

Makes sure there are no consecutive lines that are either blank or whitespace only. This reduces the need to scroll further than necessary when reading code, and increases the likelihood that a logical block of code will fit on one screen for easier comprehension.

Example of violation:

``` groovy
def name


def value



def id
```

## Further Reading

* [CodeNarc - ConsecutiveBlankLines](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#ConsecutiveBlankLines)