Pattern: Excessive block nesting

Issue: -

## Description

This rule checks for excessive nesting of conditional and looping
constructs.

You can configure if blocks are considered using the `CountBlocks`
option. When set to `false` (the default) blocks are not counted
towards the nesting level. Set to `true` to count blocks as well.

The maximum level of nesting allowed is configurable.

## Default configuration

Attribute | Value
--- | ---
CountBlocks | false
Max | 3

## Further Reading

* [RuboCop - Metrics/BlockNesting](https://docs.rubocop.org/rubocop/cops_metrics.html#metricsblocknesting)
* [https://github.com/bbatsov/ruby-style-guide#three-is-the-number-thou-shalt-count](https://github.com/bbatsov/ruby-style-guide#three-is-the-number-thou-shalt-count)
