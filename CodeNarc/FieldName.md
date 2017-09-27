Pattern: Invalid field name

Issue: -

## Description

Verifies that the name of each field matches a regular expression. By default it checks that fields that are not *static final* have field names that start with a lowercase letter and contains only letters or numbers. By default, *static final* field names start with an uppercase letter and contain only uppercase letters, numbers and underscores.

**NOTE:** This rule checks only regular *fields* of a class, not *properties*. In Groovy, *properties* are fields declared with no access modifier (public, protected, private). Thus, this rule only checks fields that specify an access modifier. For naming of *properties*, see `PropertyNameRule`.

| **Property**     | **Description**                                                                                                                                                                                        | **Default Value**        |
| --- | --- | --- |
| regex            | Specifies the default regular expression used to validate the field name. It is required and cannot be null or empty.                                                                                  | /\[a-z\]\[a-zA-Z0-9\]\*/ |
| finalRegex       | Specifies the regular expression used to validate `final` field names. It is optional. If not set, then `final` fields that are non-`static` are validated using **regex**.                            | `null`                   |
| staticRegex      | Specifies the regular expression used to validate `static` field names. It is optional. If not set, then `static` fields that are non-`final` are validated using **regex**.                           | `null`                   |
| staticFinalRegex | Specifies the regular expression used to validate `static final` field names. It is optional. If not set, then `static final` fields are validated using **finalRegex**, **staticRegex** or **regex**. | /\[A-Z\]\[A-Z0-9\_\]\*/  |
| ignoreFieldNames | Specifies one or more (comma-separated) field names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?).                          | serialVersionUID         |

The order of precedence for the regular expression properties is: **staticFinalRegex**, **finalRegex**, **staticRegex** and finally **regex**. In other words, the first regex in that list matching the modifiers for the field is the one that is applied for the field name validation.

## Further Reading

* [CodeNarc - FieldName](http://codenarc.sourceforge.net/codenarc-rules-naming.html#FieldName)