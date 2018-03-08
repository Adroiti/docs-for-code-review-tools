Pattern: Empty code comment

Issue: -

## Description

This rule checks for empty comments.

## Examples

```ruby
# bad

#
class Foo
end

# good

#
# Description of `Foo` class.
#
class Foo
end
```
#### AllowBorderComment: true (default)

```ruby
# good

def foo
end

#################

def bar
end
```
#### AllowBorderComment: false

```ruby
# bad

def foo
end

#################

def bar
end
```
#### AllowMarginComment: true (default)

```ruby
# good

#
# Description of `Foo` class.
#
class Foo
end
```
#### AllowMarginComment: false

```ruby
# bad

#
# Description of `Foo` class.
#
class Foo
end
```

## Default configuration

Attribute | Value
--- | ---
AllowBorderComment | `true`
AllowMarginComment | `true`

## Further Reading

* [RuboCop - Layout/EmptyComment](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutemptycomment)
