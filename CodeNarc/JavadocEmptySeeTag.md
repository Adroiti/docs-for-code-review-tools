Pattern: Empty `@see` tag

Issue: -

## Description

Checks for empty `@see` tags within javadoc. Known limitation: Only the first occurrence of an empty `@see` within a javadoc comment is found.

Example of violations:

``` groovy
/**
 * Sample class
 *
 * @see                                                         // violation
 */
class MyClass {

    /**
     * Return the calculated count of some stuff,
     * starting with the specified startIndex.
     *
     * @param startIndex - the starting index
     * @return the full count
     * @throws RuntimeException
     *     @see                                                 // violation
     *
     * NOTE: Only the first occurrence of an empty @see tag
     *       within a javadoc comment is found, so the
     *       following line is not flagged as a violation!!!
     * @see
     */
    int countThings(int startIndex) { }

    /**
     *@see                                                      // violation
     */
    String name = 'joe'
}
```

## Further Reading

* [CodeNarc - JavadocEmptySeeTag](https://codenarc.github.io/CodeNarc/codenarc-rules-comments.html#javadocemptyseetag-rule)