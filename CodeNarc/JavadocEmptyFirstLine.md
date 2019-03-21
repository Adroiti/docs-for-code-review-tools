Pattern: Empty first line in comment

Issue: -

## Description

Checks for javadoc comments with an empty top line.

Example of violations:

``` groovy
/**
 *                                                      // violation
 * Sample class
 *
 * @author Some Developer
 */
class MyClass {

    /**
     *                                                  // violation
     * Return the calculated count of some stuff,
     * starting with the specified startIndex.
     *
     * @param startIndex - the starting index
     * @return the full count
     * @throws RuntimeException
     */
    int countThings(int startIndex) {
    }
}
```

## Further Reading

* [CodeNarc - JavadocEmptyFirstLine](http://codenarc.sourceforge.net/codenarc-rules-comments.html#JavadocEmptyFirstLine)