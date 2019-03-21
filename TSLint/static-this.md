Pattern: Use of `this` in static method

Issue: -

## Description

Static `this` usage can be confusing for newcomers. It can also become imprecise when used with extended classes when a static `this` of a parent class no longer specifically refers to the parent class.

## Further Reading

* [TSLint - static-this](https://palantir.github.io/tslint/rules/static-this)