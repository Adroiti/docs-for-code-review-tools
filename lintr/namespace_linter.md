Pattern: Missing package/symbol in namespace call

Issue: -

## Description

Checks for missing packages and symbols in namespace calls.

Note that using `check_exports=TRUE` or `check_nonexports=TRUE` will load packages used in user code so it could potentially change the global state.

## Further Reading

* [lintr - Available linters](https://github.com/jimhester/lintr#available-linters)