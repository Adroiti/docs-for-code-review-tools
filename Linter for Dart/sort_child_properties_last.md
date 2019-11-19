Pattern: Unsorted child properties in widget instance

Issue: -

## Description

Sort child properties last in widget instance creations. This improves
readability and plays nice with UI as Code visualization in IDEs with UI as
Code Guides in editors (such as IntelliJ) where Properties in the correct order 
appear clearly associated with the constructor call and separated from the 
children.

Example of **incorrect** code:
```dart
return Scaffold(
 appBar: AppBar(
  title: Text(widget.title),
 ),
 body: Center(
  child: Column(
   children: <Widget>[
    Text(
     'You have pushed the button this many times:',
     ),
    Text(
     '$_counter',
     style: Theme.of(context).textTheme.display1,
     ),
   ],
   mainAxisAlignment: MainAxisAlignment.center,
  ),
  floatingActionButton: FloatingActionButton(
   child: Icon(Icons.add),
   onPressed: _incrementCounter,
   tooltip: 'Increment',
  ),
 ),
);
```

Example of **correct** code:
```dart
return Scaffold(
 appBar: AppBar(
  title: Text(widget.title),
 ),
 body: Center(
  mainAxisAlignment: MainAxisAlignment.center,
  child: Column(
   children: <Widget>[
    Text(
     'You have pushed the button this many times:',
     ),
    Text(
     '$_counter',
     style: Theme.of(context).textTheme.display1,
     ),
   ],
  ),
  floatingActionButton: FloatingActionButton(
   onPressed: _incrementCounter,
   tooltip: 'Increment',
   child: Icon(Icons.add),
  ),
 ),
);
```

## Further Reading

* [Linter for Dart - sort_child_properties_last](https://dart-lang.github.io/linter/lints/sort_child_properties_last.html)