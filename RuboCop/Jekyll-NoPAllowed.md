Pattern: Use of `p`

Issue: -

## Description

Avoid using `p` to print things. Use `Jekyll.logger` instead. `puts` and `p` are useful for debugging, but should never land on the master branch.