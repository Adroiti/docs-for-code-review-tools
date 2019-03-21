Pattern: Empty lines in comment

Issue: -

## Description

Checks for javadoc comments with more than one consecutive empty line. Known limitation: Only the first occurrence of consecutive empty lines
within a javadoc comment is found.

Example of violations:

``` groovy
/**
 * Description
 *
 *                                                                          // violation
 * @param startIndex - the starting index
 * @return the full count
 * @throws RuntimeException
 *
 * NOTE: Only the first occurrence of consecutive empty lines
 *       within a javadoc comment is found, so the following
 *       lines are not flagged as violations!!!
 *
 *
 */
int countThings(int startIndex) { }
```

## Further Reading

* [CodeNarc - JavadocConsecutiveEmptyLines](http://codenarc.sourceforge.net/codenarc-rules-comments.html#JavadocConsecutiveEmptyLines)