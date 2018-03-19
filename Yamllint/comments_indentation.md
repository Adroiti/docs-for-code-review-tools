Pattern: Malformed comment indentation

Issue: -

## Description

This rule enforces comments to be indented like content.

## Examples

1.  With `comments-indentation: {}`

    the following code snippet would **PASS**:

        # Fibonacci
        [0, 1, 1, 2, 3, 5]

    the following code snippet would **FAIL**:

        # Fibonacci

    > \[0, 1, 1, 2, 3, 5\]

    the following code snippet would **PASS**:

        list:
            - 2
            - 3
            # - 4
            - 5

    the following code snippet would **FAIL**:

        list:
            - 2
            - 3
        #    - 4
            - 5

    the following code snippet would **PASS**:

        # This is the first object
        obj1:
          - item A
          # - item B
        # This is the second object
        obj2: []

    the following code snippet would **PASS**:

        # This sentence
        # is a block comment

    the following code snippet would **FAIL**:

        # This sentence
         # is a block comment

## Further Reading

* [Yamllint - comments_indentation](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.comments_indentation)