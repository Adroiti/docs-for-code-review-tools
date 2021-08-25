Pattern: Use of unsafe YAML/Marshal method

Issue: -

## Description

Disallow use of YAML/Marshal methods that can trigger RCE on untrusted input.

## Further Reading

* [RuboCop - Airbnb/UnsafeYamlMarshal](https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/lib/rubocop/cop/airbnb/unsafe_yaml_marshal.rb)
