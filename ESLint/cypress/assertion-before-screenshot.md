Pattern: Assertion on the page state before taking a screenshot

Issue: -

## Description

If you take screenshots without assertions then you may get different screenshots depending on timing.

For example, if clicking a button makes some network calls and upon success, renders something, then the screenshot may sometimes have the new render and sometimes not.

This rule checks there is an assertion making sure your application state is correct before doing a screenshot. This makes sure the result of the screenshot will be consistent.

Example of **incorrect** code:

```js
cy.visit('myUrl');
cy.screenshot();
```

Example of **correct** code:

```js
cy.visit('myUrl');
cy.get('[data-test-id="my-element"]').should('be.visible');
cy.screenshot();
```

