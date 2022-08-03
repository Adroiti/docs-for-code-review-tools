Pattern: Comment over private function

Issue: -

## Description

These comments get reported because they probably explain the functionality of the private function. However private functions should be small enough and have an understandable name so that they are self-explanatory and do not need this comment in the first place.

Instead of simply removing this comment to solve this issue prefer to split up the function into smaller functions with better names if necessary. Giving the function a better, more descriptive name can also help in solving this issue.

## Further Reading

* [Detekt - CommentOverPrivateFunction](https://detekt.dev/docs/rules/comments/#commentoverprivatefunction)