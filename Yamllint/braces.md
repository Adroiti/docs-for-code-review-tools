Pattern: Malformed spacing inside `{`/`}`

Issue: -

## Description

This rule enforces the number of spaces inside braces (`{` and `}`).

## Configuration

-   `min-spaces-inside` defines the minimal number of spaces required inside braces.
-   `max-spaces-inside` defines the maximal number of spaces allowed inside braces.
-   `min-spaces-inside-empty` defines the minimal number of spaces required inside empty braces.
-   `max-spaces-inside-empty` defines the maximal number of spaces allowed inside empty braces.

## Examples

1.  With `braces: {min-spaces-inside: 0, max-spaces-inside: 0}`

    the following code snippet would **PASS**:

        object: {key1: 4, key2: 8}

    the following code snippet would **FAIL**:

        object: { key1: 4, key2: 8 }

2.  With `braces: {min-spaces-inside: 1, max-spaces-inside: 3}`

    the following code snippet would **PASS**:

        object: { key1: 4, key2: 8 }

    the following code snippet would **PASS**:

        object: { key1: 4, key2: 8   }

    the following code snippet would **FAIL**:

        object: {    key1: 4, key2: 8   }

    the following code snippet would **FAIL**:

        object: {key1: 4, key2: 8 }

3.  With `braces: {min-spaces-inside-empty: 0, max-spaces-inside-empty: 0}`

    the following code snippet would **PASS**:

        object: {}

    the following code snippet would **FAIL**:

        object: { }

4.  With `braces: {min-spaces-inside-empty: 1, max-spaces-inside-empty: -1}`

    the following code snippet would **PASS**:

        object: {         }

    the following code snippet would **FAIL**:

        object: {}

## Further Reading

* [Yamllint - braces](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.braces)