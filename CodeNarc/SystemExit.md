Pattern: Call to `System.exit()`

Issue: -

## Description

Web applications should never call `System.exit()`. A call to `System.exit()` is probably part of leftover debug code or code imported from a non-J2EE application.

## Further Reading

* [CodeNarc - SystemExit](http://codenarc.sourceforge.net/codenarc-rules-security.html#SystemExit)