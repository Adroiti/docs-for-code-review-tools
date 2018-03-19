Pattern: Unquoted truthy value

Issue: -

## Description

This rule forbids truthy values that are not quoted nor explicitly typed.

This would prevent YAML parsers from transforming `[yes, FALSE, Off]` into `[true, false, false]` or `{y: 1, yes: 2, on: 3, true: 4, True: 5}` into `{y: 1, true: 5}`.

## Examples

1.  With `truthy: {}`

    the following code snippet would **PASS**:

        boolean: true

        object: {"True": 1, 1: "True"}

        "yes":  1
        "on":   2
        "true": 3
        "True": 4

         explicit:
           string1: !!str True
           string2: !!str yes
           string3: !!str off
           encoded: !!binary |
                      True
                      OFF
                      pad==  # this decodes as 'N\xbb\x9e8Qii'
           boolean1: !!bool true
           boolean2: !!bool "false"
           boolean3: !!bool FALSE
           boolean4: !!bool True
           boolean5: !!bool off
           boolean6: !!bool NO

    the following code snippet would **FAIL**:

        object: {True: 1, 1: True}

    the following code snippet would **FAIL**:

        yes:  1
        on:   2
        true: 3
        True: 4

## Further Reading

* [Yamllint - truthy](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.truthy)