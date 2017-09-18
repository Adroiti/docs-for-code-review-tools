Pattern: Too many method parameters

Issue: -

## Description

This rule checks for methods with too many parameters.
The maximum number of parameters is configurable.
On Ruby 2.0+ keyword arguments can optionally
be excluded from the total count.

## Default configuration

Attribute | Value
--- | ---
Max | 5
CountKeywordArgs | true

## Further Reading

* [RuboCop - Metrics/ParameterLists](https://rubocop.readthedocs.io/en/latest/cops_metrics/#metricsparameterlists)
* [https://github.com/bbatsov/ruby-style-guide#too-many-params](https://github.com/bbatsov/ruby-style-guide#too-many-params)
