Pattern: Too many empty lines

Issue: -

## Description

This rule enforces number of allowed consecutive blank lines.

## Configuration

-   `max` defines the maximal number of empty lines allowed in the document.
-   `max-start` defines the maximal number of empty lines allowed at the beginning of the file. This option takes precedence over `max`.
-   `max-end` defines the maximal number of empty lines allowed at the end of the file. This option takes precedence over `max`.

## Examples

1.  With `empty-lines: {max: 1}`

    the following code snippet would **PASS**:

        - foo:
            - 1
            - 2

        - bar: [3, 4]

    the following code snippet would **FAIL**:

        - foo:
            - 1
            - 2


        - bar: [3, 4]

## Further Reading

* [Yamllint - empty_lines](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.empty_lines)