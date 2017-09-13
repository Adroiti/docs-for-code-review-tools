Pattern: Metrics/BlockLength

Issue: -

## Description

This cop checks if the length of a block exceeds some maximum value.
Comment lines can optionally be ignored.
The maximum allowed length is configurable.
The cop can be configured to ignore blocks passed to certain methods.

## Default configuration

Attribute | Value
--- | ---
CountComments | false
Max | 25
ExcludedMethods |

## Further Reading

* [RuboCop - Metrics/BlockLength](https://rubocop.readthedocs.io/en/latest/cops_metrics/#metricsblocklength)
