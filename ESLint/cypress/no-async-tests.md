Pattern: Use of async/await in Cypress test case

Issue: -

## Description

Cypress tests [that return a promise will error](https://docs.cypress.io/guides/references/error-messages.html#Cypress-detected-that-you-returned-a-promise-from-a-command-while-also-invoking-one-or-more-cy-commands-in-that-promise) and cannot run successfully. An `async` function returns a promise under the hood, so a test using an `async` function will also error.

## Rule Details

This rule disallows using `async` test functions.

Examples of **incorrect** code for this rule:

```js
describe('my feature', () => {
  it('my test case', async ()  => {
    await cy.get('.myClass')
    // other operations
  })
})
```

```js
describe('my feature', () => {
  it('my test case', async ()  => {
    cy
    .get('.myClass')
    .click()

    await someAsyncFunction()
  })
})
```

Examples of **correct** code for this rule:

```js
describe('my feature', () => {
  it('my test case', ()  => {
    cy.get('.myClass')
    // other operations
  })
})

```

## When Not To Use It

If there are genuine use-cases for using `async/await` in your test cases then you may not want to include this rule (or at least demote it to a warning).

## Further Reading

* [cypress - no-async-tests](https://github.com/cypress-io/eslint-plugin-cypress/blob/master/docs/rules/no-async-tests.md)

