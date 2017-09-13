Pattern: Metrics/BlockNesting

Issue: -

## Description

This cop checks for excessive nesting of conditional and looping
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

* [RuboCop - Metrics/BlockNesting](https://rubocop.readthedocs.io/en/latest/cops_metrics/#metricsblocknesting)
* [https://github.com/bbatsov/ruby-style-guide#three-is-the-number-thou-shalt-count](https://github.com/bbatsov/ruby-style-guide#three-is-the-number-thou-shalt-count)
