Pattern: Missing error handling for `redux-saga`

Issue: -

## Description

This rule ensures that all `redux-saga` effects are inside a try/catch block for error handling.

An uncaught error can cause all other sagas waiting to complete to be inadvertently canceled.

## Examples

```es6
import { call } from "redux-saga"

// good
function* good() {
  try {
    yield call(action)
  } catch (error) {
    yield call(handleError, error)
  }
}

// bad
function* bad() {
  call(action)
}
```