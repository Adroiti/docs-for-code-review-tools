Pattern: Malformed comment

Issue: -

## Description

This rule enforces the position and formatting of comments.

## Configuration

-   Use `require-starting-space` to require a space character right after the `#`. Set to `true` to enable, `false` to disable.
-   `min-spaces-from-content` is used to visually separate inline comments from content. It defines the minimal required number of spaces between a comment and its preceding content.

## Examples

1.  With `comments: {require-starting-space: true}`

    the following code snippet would **PASS**:

        # This sentence
        # is a block comment

    the following code snippet would **PASS**:

        ##############################
        ## This is some documentation

    the following code snippet would **FAIL**:

        #This sentence
        #is a block comment

2.  With `comments: {min-spaces-from-content: 2}`

    the following code snippet would **PASS**:

        x = 2 ^ 127 - 1  # Mersenne prime number

    the following code snippet would **FAIL**:

        x = 2 ^ 127 - 1 # Mersenne prime number

## Further Reading

* [Yamllint - comments](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.comments)