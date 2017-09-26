Pattern: Unreachable code

Issue: -

## Description

Dead code appears after a `return` statement or an exception is thrown. If code appears after one of these statements then it will never be executed and can be safely deleted.

## Further Reading

* [CodeNarc - DeadCode](http://codenarc.sourceforge.net/codenarc-rules-basic.html#DeadCode)