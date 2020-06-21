Pattern: Empty last line in comment

Issue: -

## Description

Checks for javadoc comments with an empty line at the bottom.

Example of violations:

``` groovy
/**
 * Sample class
 *
 * @author Some Developer
 *                                                      // violation
 */
class MyClass {

    /**
     * Return the calculated count of some stuff,
     * starting with the specified startIndex.
     *
     * @param startIndex - the starting index
     * @return the full count
     * @throws RuntimeException
     *                                                  // violation
     */
    int countThings(int startIndex) {
    }
}
```

## Further Reading

* [CodeNarc - JavadocEmptyLastLine](https://codenarc.github.io/CodeNarc/codenarc-rules-comments.html#javadocemptylastline-rule)