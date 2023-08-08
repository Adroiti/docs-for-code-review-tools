Pattern: Malformed spacing around exception handling keyword

Issue: -

## Description

This rule checks if empty lines exist around the bodies of `begin`
sections. This rule doesn't check empty lines at `begin` body
beginning/end and around method definition body.
`Style/EmptyLinesAroundBeginBody` or `Style/EmptyLinesAroundMethodBody`
can be used for this purpose.

## Examples

```ruby
# good

begin
  do_something
rescue
  do_something2
else
  do_something3
ensure
  do_something4
end

# good

def foo
  do_something
rescue
  do_something2
end

# bad

begin
  do_something

rescue

  do_something2

else

  do_something3

ensure

  do_something4
end

# bad

def foo
  do_something

rescue

  do_something2
end
```

## Further Reading

* [RuboCop - Layout/EmptyLinesAroundExceptionHandlingKeywords](https://docs.rubocop.org/rubocop/cops_layout.html#layoutemptylinesaroundexceptionhandlingkeywords)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies](https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies)
