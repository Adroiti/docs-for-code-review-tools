Pattern: Use of possibly unsafe `preexec_fn` parameter

Issue: -

## Description

The `preexec_fn` parameter is not safe to use in the presence of threads in your application. The child process could deadlock before `exec` is called. If you must use it, keep it trivial and minimize the number of libraries you call into.

## Further Reading

* [The Python Standard Library - Subprocess management](https://docs.python.org/3/library/subprocess.html#popen-constructor)