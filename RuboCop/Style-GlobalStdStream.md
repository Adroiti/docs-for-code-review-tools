Pattern: Malformed global input/output stream

Issue: -

## Description

This rule enforces the use of `$stdout/$stderr/$stdin` instead of `STDOUT/STDERR/STDIN`.
`STDOUT/STDERR/STDIN` are constants, and while you can actually
reassign (possibly to redirect some stream) constants in Ruby, you'll get
an interpreter warning if you do so.

## Examples

```ruby
# bad
STDOUT.puts('hello')

hash = { out: STDOUT, key: value }

def m(out = STDOUT)
  out.puts('hello')
end

# good
$stdout.puts('hello')

hash = { out: $stdout, key: value }

def m(out = $stdout)
  out.puts('hello')
end
```

## Further Reading

* [RuboCop - Style/GlobalStdStream](https://docs.rubocop.org/rubocop/cops_style.html#styleglobalstdstream)
* [The Ruby Style Guide](https://rubystyle.guide#global-stdout)