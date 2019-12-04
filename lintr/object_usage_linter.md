Pattern: Improper object usage

Issue: -

## Description

Checks that closures have the proper usage using `codetools::checkUsage()`. Note: this runs `base::eval()` on the code, so do not use with untrusted code.

## Further Reading

* [lintr - Available linters](https://github.com/jimhester/lintr#available-linters)