Pattern: Malformed spacing around `:`

Issue: -

## Description

This rule enforces the number of spaces before and after colons (`:`).

## Configuration

-   `max-spaces-before` defines the maximal number of spaces allowed before colons (use `-1` to disable).
-   `max-spaces-after` defines the maximal number of spaces allowed after colons (use `-1` to disable).

## Examples

1.  With `colons: {max-spaces-before: 0, max-spaces-after: 1}`

    the following code snippet would **PASS**:

        object:
          - a
          - b
        key: value

2.  With `colons: {max-spaces-before: 1}`

    the following code snippet would **PASS**:

        object :
          - a
          - b

    the following code snippet would **FAIL**:

        object  :
          - a
          - b

3.  With `colons: {max-spaces-after: 2}`

    the following code snippet would **PASS**:

        first:  1
        second: 2
        third:  3

    the following code snippet would **FAIL**:

        first: 1
        2nd:   2
        third: 3

## Further Reading

* [Yamllint - colons](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.colons)