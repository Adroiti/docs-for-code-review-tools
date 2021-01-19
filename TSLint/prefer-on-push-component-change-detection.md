Pattern: Missing use of `ChangeDetectionStrategy.OnPush`

Issue: -

## Description

By default Angular uses the `ChangeDetectionStrategy.Default`.

This strategy doesn’t assume anything about the application, therefore every time something changes in our application, as a result of various user events, timers, XHR, promises, etc., a change detection will run on all components.

By using `ChangeDetectionStrategy.OnPush`, Angular will only run the change detection cycle in the following cases:

- Inputs references change.
- An event originated from the component or one of its children.
- If manually called.

## Further Reading

* [TSLint - prefer-on-push-component-change-detection](http://codelyzer.com/rules/prefer-on-push-component-change-detection/)