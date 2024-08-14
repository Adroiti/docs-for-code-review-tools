Pattern: Use of `useVisibleTask$()`

Issue: -

## Description

`useVisibleTask$()` runs eagerly and blocks the main thread, preventing user interaction until the task is finished. Consider using `useTask$()`, `useOn()`, `useOnDocument()`, or `useOnWindow()` instead. 

If you have to use a `useVisibleTask$()`, you can disable the warning with a `'// eslint-disable-next-line qwik/no-use-visible-task'` comment.