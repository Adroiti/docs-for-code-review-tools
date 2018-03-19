Pattern: Duplicate mapping key

Issue: -

## Description

This rule checks for multiple entries with the same key in mappings.

## Examples

1.  With `key-duplicates: {}`

    the following code snippet would **PASS**:

        - key 1: v
          key 2: val
          key 3: value
        - {a: 1, b: 2, c: 3}

    the following code snippet would **FAIL**:

        - key 1: v
          key 2: val
          key 1: value

    the following code snippet would **FAIL**:

        - {a: 1, b: 2, b: 3}

    the following code snippet would **FAIL**:

        duplicated key: 1
        "duplicated key": 2

        other duplication: 1
        ? >-
            other
            duplication
        : 2

## Further Reading

* [Yamllint - key_duplicates](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.key_duplicates)