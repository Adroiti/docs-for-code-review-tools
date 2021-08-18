Pattern: Use of `Timeout.timeout`

Issue: -

## Description

In combination with Rails autoloading, timeout can cause Segmentation Faults in version of Ruby we use. It can also cause logic errors since it can raise in any callee scope. Use client library timeouts and monitoring to ensure proper timing behavior for web requests.

## Further Reading

* [RuboCop - Airbnb/NoTimeout](https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/lib/rubocop/cop/airbnb/no_timeout.rb)
