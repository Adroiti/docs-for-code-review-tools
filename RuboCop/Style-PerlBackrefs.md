Pattern: Use of Perl-style backreference

Issue: -

## Description

Perl-legacy variables denoting last regexp group matches (`$1`, `$2`, etc) are cryptic. Use `Regexp.last_match(n)` instead. 

## Examples

```ruby
/(regexp)/ =~ string
...

# bad
process $1

# good
process Regexp.last_match(1)
```

## Further Reading

* [RuboCop - Style/PerlBackrefs](https://docs.rubocop.org/rubocop/cops_style.html#styleperlbackrefs)
* [https://github.com/bbatsov/ruby-style-guide#no-perl-regexp-last-matchers](https://github.com/bbatsov/ruby-style-guide#no-perl-regexp-last-matchers)
