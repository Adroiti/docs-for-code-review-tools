Pattern: Bad except order

Issue: -

## Description

Used when except clauses are not in the correct order (from the more specific to the more generic). If you don't fix the order, some exceptions may not be catched by the most specific handler.

## Further Reading

* [Pylint - E0701](http://pylint-messages.wikidot.com/messages:e0701)