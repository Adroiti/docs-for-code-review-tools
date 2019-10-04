Pattern: Missing use of `data-*` attribute

Issue: -

## Description

Forces `cy.get` to allow selectors that target `data-*` attributes.

Example of **incorrect** code:

```js
cy.get(".a")
cy.get('[daedta-cy=submit]').click()
cy.get('[d-cy=submit]')
cy.get(".btn-large").click()
cy.get(".btn-.large").click()
```

Example of **correct** code:

```js
cy.get('[data-cy=submit]').click()
cy.get('[data-QA=submit]')
```

## Further Reading

* [cypress - Selecting Elements](https://docs.cypress.io/guides/references/best-practices.html#Selecting-Elements)

