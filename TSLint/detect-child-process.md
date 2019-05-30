Pattern: Unsafe use of `child_process`

Issue: -

## Description

Detects usages of `child_process` and especially `child_process.exec()`
with a non-literal first argument. It is dangerous to pass a string
constructed at runtime as the first argument to the
`child_process.exec()`. `child_process.exec(cmd)` runs `cmd` as a shell
command which could allow an attacker to execute malicious code injected
into `cmd`. Instead of `child_process.exec(cmd)` you should use
`child_process.spawn(cmd)` or specify the command as a literal, e.g.
`child_process.exec('ls')`.

## Further Reading

* [TSLint - detect-child-process](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)