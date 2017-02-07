Pattern: Bare except

Issue: -

## Description

Used when an except clause doesn't specify exceptions type to catch. Catching exceptions should be as precise as possible. The type of exceptions that can be raised should be known in advance. Using a catch-all `Exception` instance defeats the purpose of knowing the type of error that occured, and prohibits the use of tailored responses.

## Further Reading

* [Pylint - W0702](http://pylint-messages.wikidot.com/messages:w0702)
