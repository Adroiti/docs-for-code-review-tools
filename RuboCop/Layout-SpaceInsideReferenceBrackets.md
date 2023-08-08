Pattern: Malformed space inside reference brackets

Issue: -

## Description

Checks that reference brackets have or don't have surrounding space depending on configuration.

## Examples

#### EnforcedStyle: no_space (default)

```ruby
# The `no_space` style enforces that reference brackets have
# no surrounding space.

# bad
hash[ :key ]
array[ index ]

# good
hash[:key]
array[index]
```
#### EnforcedStyle: space

```ruby
# The `space` style enforces that reference brackets have
# surrounding space.

# bad
hash[:key]
array[index]

# good
hash[ :key ]
array[ index ]
```
#### EnforcedStyleForEmptyBrackets: no_space (default)

```ruby
# The `no_space` EnforcedStyleForEmptyBrackets style enforces that
# empty reference brackets do not contain spaces.

# bad
foo[ ]
foo[     ]

# good
foo[]
```
#### EnforcedStyleForEmptyBrackets: space

```ruby
# The `space` EnforcedStyleForEmptyBrackets style enforces that
# empty reference brackets contain exactly one space.

# bad
foo[]
foo[    ]

# good
foo[ ]
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | `no_space`
EnforcedStyleForEmptyBrackets | `no_space`

## Further Reading

* [RuboCop - Layout/SpaceInsideReferenceBrackets](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceinsidereferencebrackets)
