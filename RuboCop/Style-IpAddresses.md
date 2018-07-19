Pattern: Hardcoded IP address

Issue: -

## Description

Checks for hardcoded IP addresses, which can make code
brittle. IP addresses are likely to change when code
is deployed to a different server or environment, which may break
a deployment if forgotten. Prefer setting IP addresses in ENV or
other configuration.

## Examples

```ruby
# bad
ip_address = '1.2.3.4'

# good
ip_address = ENV['DEPLOYMENT_IP_ADDRESS']
```