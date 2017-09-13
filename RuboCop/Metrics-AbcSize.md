Pattern: Metrics/AbcSize

Issue: -

## Description

This cop checks that the ABC size of methods is not higher than the
configured maximum. The ABC size is based on assignments, branches
(method calls), and conditions. See http://c2.com/cgi/wiki?AbcMetric

## Default configuration

Attribute | Value
--- | ---
Max | 15

## Further Reading

* [RuboCop - Metrics/AbcSize](https://rubocop.readthedocs.io/en/latest/cops_metrics/#metricsabcsize)
* [http://c2.com/cgi/wiki?AbcMetric](http://c2.com/cgi/wiki?AbcMetric)
