Pattern: Endless method

Issue: -

## Description

This rule checks for endless methods.

It can enforce either the use of endless methods definitions
for single-lined method bodies, or disallow endless methods.

Other method definition types are not considered by this rule.

The supported styles are:
* allow_single_line (default) - only single line endless method definitions are allowed.
* allow_always - all endless method definitions are allowed.
* disallow - all endless method definitions are disallowed.

NOTE: Incorrect endless method definitions will always be
corrected to a multi-line definition.

## Examples

#### EnforcedStyle: allow_single_line (default)

```ruby
# good
def my_method() = x

# bad, multi-line endless method
def my_method() = x.foo
                   .bar
                   .baz
```

#### EnforcedStyle: allow_always

```ruby
# good
def my_method() = x

# good
def my_method() = x.foo
                   .bar
                   .baz
```

#### EnforcedStyle: disallow

```ruby
# bad
def my_method; x end

# bad
def my_method() = x.foo
                   .bar
                   .baz
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `allow_single_line` | `allow_single_line`, `allow_always`, `disallow`

## Further Reading

* [RuboCop - Style/EndlessMethod](https://docs.rubocop.org/rubocop/cops_style.html#styleendlessmethod)