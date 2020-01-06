Pattern: Misaligned element of hash

Issue: -

## Description

This rule checks that the keys, separators, and values of a multi-line hash
literal are aligned according to configuration. The configuration
options are:

  - key (left align keys)
  - separator (align hash rockets and colons, right align keys)
  - table (left align keys, hash rockets, and values)

The treatment of hashes passed as the last argument to a method call
can also be configured. The options are:

  - always_inspect
  - always_ignore
  - ignore_implicit (without curly braces)
  - ignore_explicit (with curly braces)

## Examples

```ruby
# EnforcedHashRocketStyle: key (default)
# EnforcedColonStyle: key (default)

# good
{
  foo: bar,
  ba: baz
}
{
  :foo => bar,
  :ba => baz
}

# bad
{
  foo: bar,
   ba: baz
}
{
  :foo => bar,
   :ba => baz
}
```
```ruby
# EnforcedHashRocketStyle: separator
# EnforcedColonStyle: separator

#good
{
  foo: bar,
   ba: baz
}
{
  :foo => bar,
   :ba => baz
}

#bad
{
  foo: bar,
  ba: baz
}
{
  :foo => bar,
  :ba => baz
}
{
  :foo => bar,
  :ba  => baz
}
```
```ruby
# EnforcedHashRocketStyle: table
# EnforcedColonStyle: table

#good
{
  foo: bar,
  ba:  baz
}
{
  :foo => bar,
  :ba  => baz
}

#bad
{
  foo: bar,
  ba: baz
}
{
  :foo => bar,
   :ba => baz
}
```

## Default configuration

Attribute | Value
--- | ---
EnforcedHashRocketStyle | key
SupportedHashRocketStyles | key, separator, table
EnforcedColonStyle | key
SupportedColonStyles | key, separator, table
EnforcedLastArgumentHashStyle | always_inspect
SupportedLastArgumentHashStyles | always_inspect, always_ignore, ignore_implicit, ignore_explicit

## Further Reading

* [RuboCop - Layout/HashAlignment](https://rubocop.readthedocs.io/en/latest/cops_layout/#layouthashalignment)
