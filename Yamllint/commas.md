Pattern: Malformed spacing around `,`

Issue: -

## Description

This rule enforces the number of spaces before and after commas (`,`).

## Configuration

-   `max-spaces-before` defines the maximal number of spaces allowed before commas (use `-1` to disable).
-   `min-spaces-after` defines the minimal number of spaces required after commas.
-   `max-spaces-after` defines the maximal number of spaces allowed after commas (use `-1` to disable).

## Examples

1.  With `commas: {max-spaces-before: 0}`

    the following code snippet would **PASS**:

        strange var:
          [10, 20, 30, {x: 1, y: 2}]

    the following code snippet would **FAIL**:

        strange var:
          [10, 20 , 30, {x: 1, y: 2}]

2.  With `commas: {max-spaces-before: 2}`

    the following code snippet would **PASS**:

        strange var:
          [10  , 20 , 30,  {x: 1  , y: 2}]

3.  With `commas: {max-spaces-before: -1}`

    the following code snippet would **PASS**:

        strange var:
          [10,
           20   , 30
           ,   {x: 1, y: 2}]

4.  With `commas: {min-spaces-after: 1, max-spaces-after: 1}`

    the following code snippet would **PASS**:

        strange var:
          [10, 20,30, {x: 1, y: 2}]

    the following code snippet would **FAIL**:

        strange var:
          [10, 20,30,   {x: 1,   y: 2}]

5.  With `commas: {min-spaces-after: 1, max-spaces-after: 3}`

    the following code snippet would **PASS**:

        strange var:
          [10, 20,  30,  {x: 1,   y: 2}]

6.  With `commas: {min-spaces-after: 0, max-spaces-after: 1}`

    the following code snippet would **PASS**:

        strange var:
          [10, 20,30, {x: 1, y: 2}]

## Further Reading

* [Yamllint - commas](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.commas)