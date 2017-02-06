Pattern: Unnecessary lambda

Issue: -

## Description

Used when the body of a lambda expression is a function call on the same argument list as the lambda itself; such lambda expressions are in all but a few cases replaceable with the function being called in the body of the lambda.

## Further Reading

* [Pylint - W0108](http://pylint-messages.wikidot.com/messages:w0108)