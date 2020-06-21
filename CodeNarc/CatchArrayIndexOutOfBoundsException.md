Pattern: Catching `ArrayIndexOutOfBoundsException`

Issue: -

## Description

Checks for catching a `ArrayIndexOutOfBoundsException`. Catching `ArrayIndexOutOfBoundsException` should be avoided in the first place by checking the array size before accessing an array element. Catching the exception may mask underlying errors.

## Further Reading

* [CodeNarc - CatchArrayIndexOutOfBoundsException](https://codenarc.github.io/CodeNarc/codenarc-rules-exceptions.html#catcharrayindexoutofboundsexception-rule)