Pattern: Unused variable

Issue: -

## Description

Checks for variables that are never referenced. An assignment to the variable is not considered a reference.

The rule has a property named `ignoreVariableNames`, which can be set to ignore some variable names. For instance, to ignore fields named 'unused', set the property to 'unused'.

| **Property**        | **Description**                                                                                                                                                                  | **Default Value** |
| --- | --- | --- |
| ignoreVariableNames | Specifies one or more (comma-separated) variable names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?). | `null`            |

Known limitations:

-   Incorrectly considers a variable referenced if another variable with the same name is referenced elsewhere (in another scope/block).

## Further Reading

* [CodeNarc - UnusedVariable](https://codenarc.github.io/CodeNarc/codenarc-rules-unused.html#unusedvariable-rule)