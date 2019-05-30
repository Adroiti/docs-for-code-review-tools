Pattern: Chai call with vague failure message

Issue: -

## Description

Avoid Chai assertions that result in vague errors. For example,
asserting `expect(something).to.be.true` will result in the failure
message "Expected true received false". This is a vague error message
that does not reveal the underlying problem. It is especially vague in
TypeScript because stack trace line numbers often do not match the
source code. A better pattern to follow is the xUnit Patterns [Assertion
Message](http://xunitpatterns.com/Assertion%20Message.htm) pattern. The
previous code sample could be better written as
`expect(something).to.equal(true, 'expected something to have occurred');`

## Further Reading

* [TSLint - chai-vague-errors](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)