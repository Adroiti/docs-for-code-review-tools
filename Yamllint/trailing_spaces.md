Pattern: Trailing whitespace

Issue: -

## Description

Adding trailing whitespace can cause extra work for others editing the same file, when they merge, as can removing existing trailing whitespace. So: Don't introduce trailing whitespace. Remove it if you're already changing that line, or do it in a separate clean-up operation (preferably when no-one else is working on the file).

## Examples

1.  With `trailing-spaces: {}`

    the following code snippet would **PASS**:

        this document doesn't contain
        any trailing
        spaces

    the following code snippet would **FAIL**:

		this document contains     
		trailing spaces
		on lines 1 and 3 

## Further Reading

* [Yamllint - trailing_spaces](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.trailing_spaces)