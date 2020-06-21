Pattern: Grails - `servletContext` reference

Issue: -

## Description

Rule that checks for references to the `servletContext` object from within Grails controller and taglib classes.

This rule is intended as a "governance" rule to enable monitoring and controlling access to the `servletContext` from within application source code. Storing objects in the `servletContext` may inhibit scalability and/or performance and should be carefully considered. Furthermore, access to the `servletContext` is not synchronized, so reading/writing objects from the `servletConext` must be manually synchronized.

Note that this rule does not check for direct access to the `servletContext` from within GSP (Groovy Server Pages) files.

Enabling this rule may make most sense in a team environment where team members exhibit a broad range of skill and experience levels. Appropriate `servletContext` access can be configured as exceptions to this rule by configuring either the `doNotApplyToFilenames` or `doNotApplyToFilesMatching` property of the rule.

This rule sets the default value of `applyToFilesMatching` to only match files under the 'grails-app/controllers' or 'grails-app/taglib' folders. You can override this with a different regular expression value if appropriate.

## Further Reading

* [CodeNarc - GrailsServletContextReference](https://codenarc.github.io/CodeNarc/codenarc-rules-grails.html#grailsservletcontextreference-rule)