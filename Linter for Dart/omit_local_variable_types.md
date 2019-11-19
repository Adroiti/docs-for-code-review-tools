Pattern: Use of type annotation for local variable

Issue: -

## Description

Usually the types of local variables can be easily inferred, so it isn't necessary to annotate them.

Example of **incorrect** code:
```dart
Map<int, List<Person>> groupByZip(Iterable<Person> people) {
 Map<int, List<Person>> peopleByZip = <int, List<Person>>{};
 for (Person person in people) {
  peopleByZip.putIfAbsent(person.zip, () => <Person>[]);
  peopleByZip[person.zip].add(person);
 }
 return peopleByZip;
}
```

Example of **correct** code:
```dart
Map<int, List<Person>> groupByZip(Iterable<Person> people) {
 var peopleByZip = <int, List<Person>>{};
 for (var person in people) {
  peopleByZip.putIfAbsent(person.zip, () => <Person>[]);
  peopleByZip[person.zip].add(person);
 }
 return peopleByZip;
}
```

## Further Reading

* [Linter for Dart - omit_local_variable_types](https://dart-lang.github.io/linter/lints/omit_local_variable_types.html)