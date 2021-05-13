Pattern: Prefer async pipe

Issue: -

## Description

This rule effects failures if explicit calls to `subscribe` are made within a component. Instead, use a child component to which a value is passed by using the async pipe in the parent component's template.

## Further Reading

* [GitHub - prefer-async-pipe](https://github.com/cartant/eslint-plugin-rxjs-angular/blob/main/docs/rules/prefer-async-pipe.md)