Pattern: Trailing code after method definition

Issue: -

## Description

This rule checks for trailing code after the method definition. Place the end statement of a multi-line method on its own line.

## Examples

```ruby
# bad
def some_method
do_stuff; end

def do_this(x)
  baz.map { |b| b.this(x) } end

def foo
  block do
    bar
  end end

# good
def some_method
  do_stuff
end

def do_this(x)
  baz.map { |b| b.this(x) }
end

def foo
  block do
    bar
  end
end
```

## Further Reading

* [RuboCop - Style/TrailingMethodEndStatement](https://rubocop.readthedocs.io/en/latest/cops_style/#styletrailingmethodendstatement)
