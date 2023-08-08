Pattern: ABC size is too high

Issue: -

## Description

This rule checks that the  Assignment Branch Condition (ABC) size of methods is not higher than the
configured maximum. The ABC size is based on assignments, branches
(method calls), and conditions.

## Default configuration

Attribute | Value
--- | ---
Max | 15

## Further Reading

* [RuboCop - Metrics/AbcSize](https://docs.rubocop.org/rubocop/cops_metrics.html#metricsabcsize)
* [http://c2.com/cgi/wiki?AbcMetric](http://c2.com/cgi/wiki?AbcMetric)
