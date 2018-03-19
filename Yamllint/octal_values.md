Pattern: Use of value with octal number

Issue: -

## Description

This rule forbids values with octal numbers. In YAML, numbers that start with `0` are interpreted as octal, but this is not always wanted. For instance `010` is the city code of Beijing, and should not be converted to `8`.

## Examples

1.  With `octal-values: {forbid-implicit-octal: true}`

    the following code snippets would **PASS**:

        user:
          city-code: '010'

    the following code snippets would **PASS**:

        user:
          city-code: 010,021

    the following code snippets would **FAIL**:

        user:
          city-code: 010

2.  With `octal-values: {forbid-explicit-octal: true}`

    the following code snippets would **PASS**:

        user:
          city-code: '0o10'

    the following code snippets would **FAIL**:

        user:
          city-code: 0o10

## Further Reading

* [Yamllint - octal_values](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.octal_values)