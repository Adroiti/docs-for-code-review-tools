Pattern: Grails - domain with service reference

Issue: -

## Description

Checks that Grails Domain classes do not have Service classes injected.

This rule sets the default value of `applyToFilesMatching` to only match files under the 'grails-app/domain' folder. You can override this with a different regular expression value if appropriate.

## Further Reading

* [CodeNarc - GrailsDomainWithServiceReference](http://codenarc.sourceforge.net/codenarc-rules-grails.html#GrailsDomainWithServiceReference)