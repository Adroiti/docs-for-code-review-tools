Pattern: Inconsistent linebreak style

Issue: -

## Description

Enforces a consistent linebreak style. Choose either LF (`\n`) or CRLF (`\r\n`).

## Configuration

`string`: `"unix"|"windows"`

### `"unix"`

Linebreaks _must always_ be LF (`\n`).

Lines with CRLF linebreaks are considered violations.

### `"windows"`

Linebreaks _must always_ be CRLF (`\r\n`).

Lines with LF linebreaks are considered violations.

## Further Reading

* [stylelint - linebreaks](https://stylelint.io/user-guide/rules/linebreaks)