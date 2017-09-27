Pattern: Unnecessary `catch` block

Issue: -

## Description

Violations are triggered when a *catch* block does nothing but throw the original exception. In this scenario there is usually no need for a *catch* block, just let the exception be thrown from the original code. This condition frequently occurs when catching an exception for debugging purposes but then forgetting to take the `catch` statement out.

## Further Reading

* [CodeNarc - UnnecessaryCatchBlock](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryCatchBlock)