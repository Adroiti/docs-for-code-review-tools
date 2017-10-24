Pattern: `yield` in race entry

Issue: -

## Description

This rule detects usages of `yield` in race entries.

## Examples

```es6
import { race, call } from "redux-saga"

// Good
function* good() {
  yield race({
    posts: call(fetchApis)
  })
}

function* good() {
  yield race({
    watchers: [call(watcher1), call(watcher2)]
  })
}

// Bad
function* bad() { 
  yield race({ posts: yield call(fetchApis) }) 
}

function* bad() {
  yield race({
    watchers: yield [call(watcher1), call(watcher2)]
  })
}

```