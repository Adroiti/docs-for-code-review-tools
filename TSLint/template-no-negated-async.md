Pattern: Use of negated async

Issue: -

## Description

Angular’s async pipes emit null initially, prior to the observable emitting any values, or the promise resolving. This can cause negations, like `*ngIf="!(myConditional | async)"` to thrash the layout and cause expensive side-effects like firing off XHR requests for a component which should not be shown.

## Further Reading

* [TSLint - template-no-negated-async](http://codelyzer.com/rules/template-no-negated-async/)