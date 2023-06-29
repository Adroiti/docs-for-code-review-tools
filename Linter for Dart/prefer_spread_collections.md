Pattern: Missing use of spread collection

Issue: -

## Description

Collection literals are excellent when you want to create a new collection out 
of individual items. But, when existing items are already stored in another 
collection, spread collection syntax leads to simpler code.

Example of **incorrect** code:

```
Widget build(BuildContext context) {
 return CupertinoPageScaffold(
  child: ListView(
   children: [
    Tab2Header(),
   ]..addAll(buildTab2Conversation()),
  ),
 );
}
```

```
var ints = [1, 2, 3];
print(['a']..addAll(ints.map((i) => i.toString()))..addAll(['c']));
```

```
var things;
var l = ['a']..addAll(things ?? const []);
```


Example of **correct** code:

```
Widget build(BuildContext context) {
 return CupertinoPageScaffold(
  child: ListView(
   children: [
    Tab2Header(),
    ...buildTab2Conversation(),
   ],
  ),
 );
}
```

```
var ints = [1, 2, 3];
print(['a', ...ints.map((i) => i.toString()), 'c');
```

```
var things;
var l = ['a', ...?things];
```

## Further Reading

* [Linter for Dart - prefer_spread_collections](https://dart.dev/tools/linter-rules/prefer_spread_collections)