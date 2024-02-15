Pattern: Malformed comma after last item in array

Issue: -

## Description

Enforce/forbid a comma after the last item in an array declaration.

By default, this sniff will:
* Forbid a comma after the last array item for single-line arrays.
* Enforce a comma after the last array item for multi-line arrays.

This can be changed for each type or array individually by setting the `singleLine` and/or `multiLine` properties in a custom ruleset.

Use any of the following values to change the properties: `enforce`, `forbid` or `skip` to not check the comma after the last array item for a particular type of array.

The default for the `singleLine` property is `forbid`. The default for the `multiLine` property is `enforce`.

## Further Reading

* [NormalizedArrays.Arrays.CommaAfterLast](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#normalizedarrays)