Pattern: Grails - public controller method

Issue: -

## Description

**NOTE:** This rule has been disabled by default (i.e., by setting its *enabled* property to *false*). Given that Grails 2.x allows and encourages controller actions to be defined as methods instead of closures, this rule makes no sense for Grails 2.x projects.

Rule that checks for public methods on Grails controller classes. Static methods are ignored.

Grails controller actions and interceptors are defined as properties on the controller class. Public methods on a controller class are unnecessary. They break encapsulation and can be confusing.

| **Property**      | **Description**                                                                                                                                                                | **Default Value** |
| --- | --- | --- |
| ignoreMethodNames | Specifies one or more (comma-separated) method names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?). | `null`            |

This rule sets the default value of `applyToFilesMatching` to only match files under the 'grails-app/controllers' folder. You can override this with a different regular expression value if appropriate.

This rule also sets the default value of `applyToClassNames` to only match class names ending in `Controller`. You can override this with a different class name pattern (String with wildcards) if appropriate.

## Further Reading

* [CodeNarc - GrailsPublicControllerMethod](https://codenarc.github.io/CodeNarc/codenarc-rules-grails.html#grailspubliccontrollermethod-rule-disabled)