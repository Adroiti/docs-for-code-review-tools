Pattern: Use of `puts`

Issue: -

## Description

Avoid using `puts` to print things. Use `Jekyll.logger` instead. `puts` and `p` are useful for debugging, but should never land on the master branch.