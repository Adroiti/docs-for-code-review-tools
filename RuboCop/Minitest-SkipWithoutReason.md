Pattern: Skipped test without reason

Issue: -

## Description

Checks for skipped tests missing the skipping reason.

## Examples

``` ruby
# bad
skip
skip('')

# bad
if condition?
  skip
else
  skip
end

# good
skip("Reason why the test was skipped")

# good
skip if condition?

```