Pattern: Missing `@exception` description in Javadoc

Issue: -

## Description

Checks for missing description within `@exception` Javadoc tags.

Known limitation: Only the first occurrence of a missing description for an `@exception` Javadoc comment is found.

Example of violations:

``` groovy
/**
 * Return the calculated count of some stuff.
 *
 * @param startIndex the starting index; must be >= 0
 * @return the full count
 * @exception RuntimeException                   // violation
 */
int countThings(int startIndex) { }
```

## Further Reading

* [CodeNarc - JavadocMissingExceptionDescription](https://codenarc.github.io/CodeNarc/codenarc-rules-comments.html#javadocmissingexceptiondescription-rule)