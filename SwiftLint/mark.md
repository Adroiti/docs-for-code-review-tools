Pattern: Invalid `MARK` comment

Issue: -

## Description

`MARK` comment should be in valid format. e.g. `// MARK: ...` or `// MARK: - ...`

Examples of **correct** code:
```swift
// MARK: good


// MARK: - good


// MARK: -


// BOOKMARK


//BOOKMARK


// BOOKMARKS

```
Examples of **incorrect** code:
```swift

↓//MARK: bad


↓// MARK:bad


↓//MARK:bad


↓//  MARK: bad


↓// MARK:  bad


↓// MARK: -bad


↓// MARK:- bad


↓// MARK:-bad


↓//MARK: - bad


↓//MARK:- bad


↓//MARK: -bad


↓//MARK:-bad


↓//Mark: bad


↓// Mark: bad


↓// MARK bad


↓//MARK bad


↓// MARK - bad


↓//MARK:- Top-Level bad mark
↓//MARK:- Another bad mark
struct MarkTest {}
↓// MARK:- Bad mark
extension MarkTest {}

```

## Further Reading

* [Stackoverflow - Swift: Understanding // MARK](https://stackoverflow.com/questions/35963128/swift-understanding-mark)
* [SwiftLint - Mark](https://realm.github.io/SwiftLint/mark.html)