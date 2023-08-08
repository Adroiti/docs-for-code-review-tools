Pattern: Block has too many lines

Issue: -

## Description

This rule checks if the length of a block exceeds some maximum value.
Comment lines can optionally be ignored.
The maximum allowed length is configurable.
The rule can be configured to ignore blocks passed to certain methods.

## Default configuration

Attribute | Value
--- | ---
CountComments | false
Max | 25
ExcludedMethods |

## Further Reading

* [RuboCop - Metrics/BlockLength](https://docs.rubocop.org/rubocop/cops_metrics.html#metricsblocklength)
