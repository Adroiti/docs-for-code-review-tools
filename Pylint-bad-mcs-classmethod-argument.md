Pattern: Bad mcs classmethod argument

Issue: -

## Description

Used when a metaclass class method has a first argument named differently than the value specified in valid-metaclass-classmethod-first-arg option (default to "mcs"), recommended to easily differentiate them from regular instance methods.

## Further Reading

* [Pylint - C0204](http://pylint-messages.wikidot.com/messages:c0204)