Pattern: Use of action in the middle of chain

Issue: -

## Description

The following test might have problems if:

    Your JS framework re-rendered asynchronously
    Your app code reacted to an event firing and removed the element

Example of **incorrect** code:

```js
cy.get('.new-todo')
  .type('todo A{enter}') // action
  .type('todo B{enter}') // action after another action - bad
  .should('have.class', 'active') // assertion after an action - bad
```

Example of **correct** code:

```js
cy.get('.new-todo').type('todo A{enter}')
cy.get('.new-todo').type('todo B{enter}')
cy.get('.new-todo').should('have.class', 'active')
```

## Further Reading

* [cypress - unsafe-to-chain-command](https://github.com/cypress-io/eslint-plugin-cypress/blob/master/docs/rules/unsafe-to-chain-command.md)

