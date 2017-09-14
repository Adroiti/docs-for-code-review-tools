Pattern: Use of Perl-style backreference

Issue: -

## Description

Perl-legacy variables denoting last regexp group matches (`$1`, `$2`, etc) are cryptic. Use `Regexp.last_match(n)` instead. 

### Example

```ruby
/(regexp)/ =~ string
...

# bad
process $1

# good
process Regexp.last_match(1)
```

## Further Reading

* [RuboCop - Style/PerlBackrefs](https://rubocop.readthedocs.io/en/latest/cops_style/#styleperlbackrefs)
* [https://github.com/bbatsov/ruby-style-guide#no-perl-regexp-last-matchers](https://github.com/bbatsov/ruby-style-guide#no-perl-regexp-last-matchers)
