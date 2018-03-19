Pattern: Line is too long

Issue: -

## Description

Your source code should not contain very long lines. The default wrapping in most tools disrupts the visual structure of the code, making it more difficult to understand.

## Configuration

-   `max` defines the maximal (inclusive) length of lines.
-   `allow-non-breakable-words` is used to allow non breakable words (without spaces inside) to overflow the limit. This is useful for long URLs, for instance. Use `true` to allow, `false` to forbid.
-   `allow-non-breakable-inline-mappings` implies `allow-non-breakable-words` and extends it to also allow non-breakable words in inline mappings.

## Examples

1.  With `line-length: {max: 70}`

    the following code snippet would **PASS**:

        long sentence:
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua.

    the following code snippet would **FAIL**:

        long sentence:
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
          tempor incididunt ut labore et dolore magna aliqua.

2.  With `line-length: {max: 60, allow-non-breakable-words: true}`

    the following code snippet would **PASS**:

        this:
          is:
            - a:
                http://localhost/very/very/very/very/very/very/very/very/long/url

        # this comment is too long,
        # but hard to split:
        # http://localhost/another/very/very/very/very/very/very/very/very/long/url

    the following code snippet would **FAIL**:

        - this line is waaaaaaaaaaaaaay too long but could be easily split...

    and the following code snippet would also **FAIL**:

        - foobar: http://localhost/very/very/very/very/very/very/very/very/long/url

3.  With `line-length: {max: 60, allow-non-breakable-words: true, allow-non-breakable-inline-mappings: true}`

    the following code snippet would **PASS**:

        - foobar: http://localhost/very/very/very/very/very/very/very/very/long/url

4.  With `line-length: {max: 60, allow-non-breakable-words: false}`

    the following code snippet would **FAIL**:

        this:
          is:
            - a:
                http://localhost/very/very/very/very/very/very/very/very/long/url

## Further Reading

* [Yamllint - line_length](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.line_length)