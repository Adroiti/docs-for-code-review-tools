Pattern: Duplicate number literal

Issue: -

## Description

This rule checks for duplicate number literals within the current class.

Code containing duplicate *Number* literals can usually be improved by declaring the *Number* as a constant field.

By default, the rule does not analyze test files. This rule sets the default value of the *doNotApplyToFilesMatching* property to ignore file names ending in 'Test.groovy', 'Tests.groovy' or 'TestCase.groovy'.

| **Property**  | **Description**                                                                                    | **Default Value** |
| --- | --- | --- |
| ignoreNumbers | The optional comma-separated list of numbers that should be ignored (i.e., not cause a violation). | `0,1`             |

## Notes

-   This rule ignores `Long`/`long` values within enums, because the generated code may include generated long id values and produce false positive rule violations.
-   This rule does not search across several files at once, only in the current file, and only within the current class.
-   You can suppress the error by annotating a class or method with the `@SuppressWarnings('DuplicateNumberLiteral')` annotation.

## Further Reading

* [CodeNarc - DuplicateNumberLiteral](http://codenarc.sourceforge.net/codenarc-rules-dry.html#DuplicateNumberLiteral)