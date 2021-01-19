Pattern: Use of `outputs` metadata property

Issue: -

## Description

- It is easier and more readable to identify which properties in a class are events.
- If you ever need to rename the event associated with `@Output`, you can modify it in a single place.
- The metadata declaration attached to the directive is shorter and thus more readable.

## Further Reading

* [TSLint - no-outputs-metadata-property](http://codelyzer.com/rules/no-outputs-metadata-property/)