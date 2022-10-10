Pattern: Use of dot import

Issue: -

## Description

Importing with `.` makes the programs much harder to understand because it is unclear whether names belong to the current package or to an imported package.

More information [here](https://github.com/golang/go/wiki/CodeReviewComments#import-dot).

## Further Reading

* [Revive - dot-imports](https://revive.run/r#dot-imports)