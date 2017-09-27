Pattern: Invalid property name

Issue: -

## Description

Verifies that the name of each property matches a regular expression. By default it checks that property names (other than *static final*) start with a lowercase letter and contains only letters or numbers. By default, *static final* property names start with an uppercase letter and contain only uppercase letters, numbers and underscores.

**NOTE:** This rule checks only *properties* of a class, not regular *fields*. In Groovy, *properties* are fields declared with no access modifier (public, protected, private). For naming of regular *fields*, see `FieldNameRule`.

| **Property**        | **Description**                                                                                                                                                                                             | **Default Value**        |
| --- | --- | --- |
| regex               | Specifies the default regular expression used to validate the property name. It is required and cannot be null or empty.                                                                                    | /\[a-z\]\[a-zA-Z0-9\]\*/ |
| finalRegex          | Specifies the regular expression used to validate `final` property names. It is optional. If not set, then `final` properties that are non-`static` are validated using **regex**.                          | `null`                   |
| staticRegex         | Specifies the regular expression used to validate `static` property names. It is optional. If not set, then `static` properties that are non-`final` are validated using **regex**.                         | `null`                   |
| staticFinalRegex    | Specifies the regular expression used to validate `static final` property names. It is optional. If not set, then `static final` property are validated using **finalRegex**, **staticRegex** or **regex**. | /\[A-Z\]\[A-Z0-9\_\]\*/  |
| ignorePropertyNames | Specifies one or more (comma-separated) property names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?).                            | `null`                   |

The order of precedence for the regular expression properties is: **staticFinalRegex**, **finalRegex**, **staticRegex** and finally **regex**. In other words, the first regex in that list matching the modifiers for the property is the one that is applied for the field name validation.

## Further Reading

* [CodeNarc - PropertyName](http://codenarc.sourceforge.net/codenarc-rules-naming.html#PropertyName)