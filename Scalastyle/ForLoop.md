Pattern: Missing use of parentheses in `for` loop

Issue: -

## Description

For-comprehensions which lack a `yield` clause is actually a loop rather than a functional comprehension and it is usually more readable to string the generators together between parentheses rather than using the syntactically-confusing `} {` construct:

```scala
for (x <- board.rows; y <- board.files) {
  printf("(%d, %d)", x, y)
}
```

is preferred to

```scala
for {
  x <- board.rows
  y <- board.files
} {
  printf("(%d, %d)", x, y)
}
```

### Example configuration
```xml
<check enabled="true" class="org.scalastyle.scalariform.ForLoopChecker" level="warning"/>
```

## Further Reading

* [Scalastyle - ForLoop](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_ForLoopChecker)