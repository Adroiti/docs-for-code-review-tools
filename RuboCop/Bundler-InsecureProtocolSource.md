Pattern: Insecure protocol source

Issue: -

## Description

The symbol argument `:gemcutter`, `:rubygems` and `:rubyforge`
are deprecated. Please change your source to URL string that uses 
'https://rubygems.org' if possible, or 'http://rubygems.org' if not.

### Example

```ruby
# bad
source :gemcutter
source :rubygems
source :rubyforge

# good
source 'https://rubygems.org' # strongly recommended
source 'http://rubygems.org'
```

## Default configuration

Attribute | Value
--- | ---
Include | \*\*/Gemfile, \*\*/gems.rb

## Further Reading

* [RuboCop - Bundler/InsecureProtocolSource](https://rubocop.readthedocs.io/en/latest/cops_bundler/#bundlerinsecureprotocolsource)
