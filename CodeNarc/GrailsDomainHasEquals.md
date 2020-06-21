Pattern: Grails - domain has `equals()`

Issue: -

## Description

Checks that Grails domain classes redefine `equals()`.

Ignores classes annotated with `@EqualsAndHashCode` or `@Canonical`.

This rule sets the default value of `applyToFilesMatching` to only match files under the 'grails-app/domain' folder. You can override this with a different regular expression value if appropriate.

## Further Reading

* [CodeNarc - GrailsDomainHasEquals](https://codenarc.github.io/CodeNarc/codenarc-rules-grails.html#grailsdomainhasequals-rule)