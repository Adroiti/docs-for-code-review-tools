Pattern: Inconsistent linebreak

Issue: -

## Description

Specify unix or windows linebreaks.

## Options

`string`: `"unix"|"windows"`

### `"unix"`

Linebreaks _must always_ be LF (`\n`).

Lines with CRLF linebreaks are considered problems.

### `"windows"`

Linebreaks _must always_ be CRLF (`\r\n`).

Lines with LF linebreaks are considered problems.

## Further Reading

* [@stylistic/linebreaks](https://github.com/stylelint-stylistic/stylelint-stylistic/blob/main/lib/rules/linebreaks/README.md)