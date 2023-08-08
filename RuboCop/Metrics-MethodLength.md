Pattern: Method has too many lines

Issue: -

## Description

This rule checks if the length of a method exceeds some maximum value.
Comment lines can optionally be ignored.
The maximum allowed length is configurable.

## Default configuration

Attribute | Value
--- | ---
CountComments | false
Max | 10

## Further Reading

* [RuboCop - Metrics/MethodLength](https://docs.rubocop.org/rubocop/cops_metrics.html#metricsmethodlength)
* [https://github.com/bbatsov/ruby-style-guide#short-methods](https://github.com/bbatsov/ruby-style-guide#short-methods)
