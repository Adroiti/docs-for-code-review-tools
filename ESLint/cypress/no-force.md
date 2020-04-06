Pattern: Use of `force: true` with action command

Issue: -

## Description

Using `force: true` on inputs appears to be confusing rather than helpful.
It usually silences the actual problem instead of providing a way to overcome it.

Example of **incorrect** code:

```js

cy.get('button').click({force: true})
cy.get('button').dblclick({force: true})
cy.get('input').type('somth', {force: true})
cy.get('div').find('.foo').find('.bar').trigger('change', {force: true})
cy.get('input').trigger('click', {force: true})
cy.get('input').rightclick({force: true})
cy.get('input').check({force: true})
cy.get('input').select({force: true})
cy.get('input').focus({force: true})

```

Example of **correct** code:

```js

cy.get('button').click()
cy.get('button').click({multiple: true})
cy.get('button').dblclick()
cy.get('input').type('somth')
cy.get('input').trigger('click', {anyoption: true})
cy.get('input').rightclick({anyoption: true})
cy.get('input').check()
cy.get('input').select()
cy.get('input').focus()

```

## Further Reading

* [cypress - no-force](https://github.com/cypress-io/eslint-plugin-cypress/blob/master/docs/rules/no-force.md)

