Pattern: Empty `@since` tag

Issue: -

## Description

Checks for empty `@since` tags within javadoc. Known limitation: Only the first occurrence of an empty `@since` within a javadoc comment is found.

Example of violations:

``` groovy
/**
 * Return the calculated count of some stuff.
 *
 * @param startIndex - the starting index
 * @return the count
 * @since                                          // violation
 */
int countThings(int startIndex) { }
```

## Further Reading

* [CodeNarc - JavadocEmptySinceTag](https://codenarc.github.io/CodeNarc/codenarc-rules-comments.html#javadocemptysincetag-rule)