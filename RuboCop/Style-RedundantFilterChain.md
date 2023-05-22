Pattern: Redundant filter chain

Issue: -

## Description

Identifies usages of `any?`, `empty?` or `none?` predicate methods chained to `select`/`filter`/`find_all` and change them to use predicate method instead.

## Examples

```ruby
@example
  # bad
  arr.select { |x| x > 1 }.any?

  # good
  arr.any? { |x| x > 1 }

  # bad
  arr.select { |x| x > 1 }.empty?
  arr.select { |x| x > 1 }.none?

  # good
  arr.none? { |x| x > 1 }

  # good
  relation.select(:name).any?
  arr.select { |x| x > 1 }.any?(&:odd?)

@example AllCops:ActiveSupportExtensionsEnabled: false (default)
  # good
  arr.select { |x| x > 1 }.many?

@example AllCops:ActiveSupportExtensionsEnabled: true
  # bad
  arr.select { |x| x > 1 }.many?

  # good
  arr.many? { |x| x > 1 }
```

## Further Reading

* [RuboCop - Style/RedundantFilterChain](https://github.com/rubocop/rubocop/blob/master/lib/rubocop/cop/style/redundant_filter_chain.rb)
