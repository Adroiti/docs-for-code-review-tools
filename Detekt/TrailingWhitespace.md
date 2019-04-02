Pattern: Trailing whitespace

Issue: -

## Description

Adding trailing whitespace can cause extra work for others editing the same file, when they merge, as can removing existing trailing whitespace. So: Don't introduce trailing whitespace. Remove it if you're already changing that line, or do it in a separate clean-up operation (preferably when no-one else is working on the file).

## Further Reading

* [Detekt - TrailingWhitespace](https://arturbosch.github.io/detekt/style.html#trailingwhitespace)