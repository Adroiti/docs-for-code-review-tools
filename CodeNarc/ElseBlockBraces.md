Pattern: Missing brace for `else`

Issue: -

## Description

Checks that *else* blocks use braces, even for a single statement.

By default, braces are not required for an *else* if it is followed immediately by an *if*. Set the `racesRequiredForElseIf` property to true to require braces is that situation as well.

## Further Reading

* [CodeNarc - ElseBlockBraces](http://codenarc.sourceforge.net/codenarc-rules-braces.html#ElseBlockBraces)