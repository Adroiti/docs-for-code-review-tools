Pattern: Mocha code with side effects

Issue: -

## Description

All test logic in a Mocha test case should be within Mocha lifecycle
method and not defined statically to execute when the module loads. Put
all assignments and initialization statements in a `before()`,
`beforeEach()`, `beforeAll()`, `after()`, `afterEach()`, `afterAll()`,
or `it()` function. Code executed outside of these lifecycle methods can
throw exceptions before the test runner is initialized and can result in
errors or even test runner crashes. 

This rule can be configured with a Regex to ignore certain initializations. For example, to ignore any
calls to `RestDataFactory` configure the rule with: `[true, { ignore: '^RestDataFactory\\..*' }]`

## Further Reading

* [TSLint - mocha-no-side-effect-code](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)