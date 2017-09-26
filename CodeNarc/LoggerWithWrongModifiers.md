Pattern: Logger with wrong modifier

Issue: -

## Description

Logger objects should be declared private, static and final.

This rule has a property: `allowProtectedLogger`, which defaults to false. Set it to true if you believe subclasses should have access to a Logger in a parent class and that Logger should be declared protected or public.

This rule has a property: `allowNonStaticLogger`, which defaults to false. Set it to true if you believe a logger should be allowed to be non-static.

## Further Reading

* [CodeNarc - LoggerWithWrongModifiers](http://codenarc.sourceforge.net/codenarc-rules-logging.html#LoggerWithWrongModifiers)