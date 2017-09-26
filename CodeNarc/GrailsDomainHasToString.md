Pattern: Grails - domain has `toString()`

Issue: -

## Description

Checks that Grails domain classes redefine `toString()`.

Ignores classes annotated with `@ToString` or `@Canonical`.

This rule sets the default value of `applyToFilesMatching` to only match files under the 'grails-app/domain' folder. You can override this with a different regular expression value if appropriate.

## Further Reading

* [CodeNarc - GrailsDomainHasToString](http://codenarc.sourceforge.net/codenarc-rules-grails.html#GrailsDomainHasToString)