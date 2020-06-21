Pattern: Missing `@throws` description in Javadoc

Issue: -

## Description

Checks for missing description within Javadoc `@throws` tags.

Known limitation: Only the first occurrence of a missing description for a `@throws` Javadoc comment is found.

Example of violations:

``` groovy
/**
 * Return the calculated count of some stuff.
 *
 * @param startIndex the starting index; must be >= 0
 * @return the full count
 * @throws RuntimeException                   // violation
 */
int countThings(int startIndex) { }
```

## Further Reading

* [CodeNarc - JavadocMissingThrowsDescription](https://codenarc.github.io/CodeNarc/codenarc-rules-comments.html#javadocmissingthrowsdescription-rule)