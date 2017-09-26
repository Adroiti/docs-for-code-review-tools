Pattern: Line is too long

Issue: -

## Description

Checks the maximum length for each line of source code. It checks for number of characters, so lines that include tabs may appear longer than the allowed number when viewing the file. The maximum line length can be configured by setting the length property, which defaults to 120.

NOTE: This rule does not support the `@SuppressAnnotations` annotation or the classname-based rule properties (applyToClassNames, doNotApplyToClassNames) to enable/disable the rule. If you want to specify or restrict where this rule is applied, you must use the file-based rule properties: applyToFileNames, doNotApplyToFileNames, applyToFilesMatching and doNotApplyToFilesMatching.

| **Property**            | **Description**                                                   | **Default Value** |
| --- | --- | --- |
| length                  | The maximum line length allowed.                                  | 120               |
| ignoreImportStatements  | If `true`, then do not apply this rule to import statements.      | `true`            |
| ignorePackageStatements | If `true`, then do not apply this rule to package statements.     | `true`            |
| ignoreLineRegex         | If specified, then ignore lines matching this regular expression. | `null`            |

## Further Reading

* [CodeNarc - LineLength](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#LineLength)