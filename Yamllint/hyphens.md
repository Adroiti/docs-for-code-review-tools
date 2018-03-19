Pattern: Malformed spacing after `-`

Issue: -

## Description

This rule enforces the number of spaces after hyphens (`-`).

## Configuration

-   `max-spaces-after` defines the maximal number of spaces allowed after hyphens.

## Examples

1.  With `hyphens: {max-spaces-after: 1}`

    the following code snippet would **PASS**:

        - first list:
            - a
            - b
        - - 1
          - 2
          - 3

    the following code snippet would **FAIL**:

        -  first list:
             - a
             - b

    the following code snippet would **FAIL**:

        - - 1
          -  2
          - 3

2.  With `hyphens: {max-spaces-after: 3}`

    the following code snippet would **PASS**:

        -   key
        -  key2
        - key42

    the following code snippet would **FAIL**:

        -    key
        -   key2
        -  key42

## Further Reading

* [Yamllint - hyphens](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.hyphens)