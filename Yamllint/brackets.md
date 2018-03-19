Pattern: Malformed spacing inside `[`/`]`

Issue: -

## Description

This rule enforces the number of spaces inside brackets (`[` and `]`).

## Configuration

-   `min-spaces-inside` defines the minimal number of spaces required inside brackets.
-   `max-spaces-inside` defines the maximal number of spaces allowed inside brackets.
-   `min-spaces-inside-empty` defines the minimal number of spaces required inside empty brackets.
-   `max-spaces-inside-empty` defines the maximal number of spaces allowed inside empty brackets.

## Examples

1.  With `brackets: {min-spaces-inside: 0, max-spaces-inside: 0}`

    the following code snippet would **PASS**:

        object: [1, 2, abc]

    the following code snippet would **FAIL**:

        object: [ 1, 2, abc ]

2.  With `brackets: {min-spaces-inside: 1, max-spaces-inside: 3}`

    the following code snippet would **PASS**:

        object: [ 1, 2, abc ]

    the following code snippet would **PASS**:

        object: [ 1, 2, abc   ]

    the following code snippet would **FAIL**:

        object: [    1, 2, abc   ]

    the following code snippet would **FAIL**:

        object: [1, 2, abc ]

3.  With `brackets: {min-spaces-inside-empty: 0, max-spaces-inside-empty: 0}`

    the following code snippet would **PASS**:

        object: []

    the following code snippet would **FAIL**:

        object: [ ]

4.  With `brackets: {min-spaces-inside-empty: 1, max-spaces-inside-empty: -1}`

    the following code snippet would **PASS**:

        object: [         ]

    the following code snippet would **FAIL**:

        object: []

## Further Reading

* [Yamllint - brackets](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.brackets)