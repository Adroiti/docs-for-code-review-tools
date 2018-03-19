Pattern: Malformed use of `...`

Issue: -

## Description

This rule requires or forbids the use of document end marker (`...`).

## Configuration

-   Set `present` to `true` when the document end marker is required, or to `false` when it is forbidden.

## Examples

1.  With `document-end: {present: true}`

    the following code snippet would **PASS**:

        ---
        this:
          is: [a, document]
        ...
        ---
        - this
        - is: another one
        ...

    the following code snippet would **FAIL**:

        ---
        this:
          is: [a, document]
        ---
        - this
        - is: another one
        ...

2.  With `document-end: {present: false}`

    the following code snippet would **PASS**:

        ---
        this:
          is: [a, document]
        ---
        - this
        - is: another one

    the following code snippet would **FAIL**:

        ---
        this:
          is: [a, document]
        ...
        ---
        - this
        - is: another one

## Further Reading

* [Yamllint - document_end](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.document_end)