Pattern: Metrics/MethodLength

Issue: -

## Description

This cop checks if the length of a method exceeds some maximum value.
Comment lines can optionally be ignored.
The maximum allowed length is configurable.

## Default configuration

Attribute | Value
--- | ---
CountComments | false
Max | 10

## Further Reading

* [RuboCop - Metrics/MethodLength](https://rubocop.readthedocs.io/en/latest/cops_metrics/#metricsmethodlength)
* [https://github.com/bbatsov/ruby-style-guide#short-methods](https://github.com/bbatsov/ruby-style-guide#short-methods)
