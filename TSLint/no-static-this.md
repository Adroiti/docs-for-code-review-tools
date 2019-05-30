Pattern: Use of `this` in static method

Issue: -

## Description

Ban the use of `this` in static methods.

__Rationale:__ It's pretty hard to wrap your head around the meaning of `this` in a static context. Especially newcomers will not recognize, that you are in fact referencing the `class` (or the `constructor` to be more precise).

## Further Reading

* [TSLint - no-static-this](https://github.com/ajafff/tslint-consistent-codestyle/blob/master/docs/no-static-this.md)