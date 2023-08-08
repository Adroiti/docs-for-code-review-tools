Pattern: Malformed space inside array literal brackets

Issue: -

## Description

Checks that brackets used for array literals have or don't have surrounding space depending on configuration.

## Examples

#### EnforcedStyle: space

```ruby
# The `space` style enforces that array literals have
# surrounding space.

# bad
array = [a, b, c, d]

# good
array = [ a, b, c, d ]
```
#### EnforcedStyle: no_space (default)

```ruby
# The `no_space` style enforces that array literals have
# no surrounding space.

# bad
array = [ a, b, c, d ]

# good
array = [a, b, c, d]
```
#### EnforcedStyle: compact

```ruby
# The `compact` style normally requires a space inside
# array brackets, with the exception that successive left
# or right brackets are collapsed together in nested arrays.

# bad
array = [ a, [ b, c ] ]

# good
array = [ a, [ b, c ]]
```
#### EnforcedStyleForEmptyBrackets: no_space (default)

```ruby
# The `no_space` EnforcedStyleForEmptyBrackets style enforces that
# empty array brackets do not contain spaces.

# bad
foo = [ ]
bar = [     ]

# good
foo = []
bar = []
```
#### EnforcedStyleForEmptyBrackets: space

```ruby
# The `space` EnforcedStyleForEmptyBrackets style enforces that
# empty array brackets contain exactly one space.

# bad
foo = []
bar = [    ]

# good
foo = [ ]
bar = [ ]
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | `no_space`
EnforcedStyleForEmptyBrackets | `no_space`

## Further Reading

* [RuboCop - Layout/SpaceInsideArrayLiteralBrackets](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceinsidearrayliteralbrackets)
