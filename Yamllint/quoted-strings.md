Pattern: Malformed quoted strings

Issue: -

## Description

Use this rule to forbid any string values that are not quoted, or to prevent quoted strings without needing it. You can also enforce the type of the quote used.

## Examples

1.  With `quoted-strings: {quote-type: any, required: true}`

    the following code snippet would **PASS**:

		foo: "bar"
		bar: 'foo'
		number: 123
		boolean: true

    the following code snippet would **FAIL**:

		foo: bar
		
2.  With `quoted-strings: {quote-type: single, required: only-when-needed}`

    the following code snippet would **PASS**:

		foo: bar
		bar: foo
		not_number: '123'
		not_boolean: 'true'
		not_comment: '# comment'
		not_list: '[1, 2, 3]'
		not_map: '{a: 1, b: 2}'

    the following code snippet would **FAIL**:

		foo: 'bar'
		
3.  With `quoted-strings: {required: false, extra-required: [^http://, ^ftp://]}`

    the following code snippet would **PASS**:

		- localhost
		- "localhost"
		- "http://localhost"
		- "ftp://localhost"

    the following code snippet would **FAIL**:

		- http://localhost
		- ftp://localhost
		
4.  With `quoted-strings: {required: only-when-needed, extra-allowed: [^http://, ^ftp://], extra-required: [QUOTED]}`

    the following code snippet would **PASS**:

		- localhost
		- "http://localhost"
		- "ftp://localhost"
		- "this is a string that needs to be QUOTED"

    the following code snippet would **FAIL**:

		- "localhost"
		- this is a string that needs to be QUOTED

## Further Reading

* [Yamllint - quoted-strings](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.quoted_strings)