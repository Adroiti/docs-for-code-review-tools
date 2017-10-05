Pattern: Misaligned parameter of multi-line method

Issue: -

## Description

Function parameters should be aligned vertically if they're in multiple lines in a declaration.

Examples of **correct** code:
```swift
func validateFunction(_ file: File, kind: SwiftDeclarationKind,
                      dictionary: [String: SourceKitRepresentable]) { }


func validateFunction(_ file: File, kind: SwiftDeclarationKind,
                      dictionary: [String: SourceKitRepresentable]) -> [StyleViolation]


func foo(bar: Int)


func foo(bar: Int) -> String 


func validateFunction(_ file: File, kind: SwiftDeclarationKind,
                      dictionary: [String: SourceKitRepresentable])
                      -> [StyleViolation]


func validateFunction(
   _ file: File, kind: SwiftDeclarationKind,
   dictionary: [String: SourceKitRepresentable]) -> [StyleViolation]


func validateFunction(
   _ file: File, kind: SwiftDeclarationKind,
   dictionary: [String: SourceKitRepresentable]
) -> [StyleViolation]


func regex(_ pattern: String,
           options: NSRegularExpression.Options = [.anchorsMatchLines,
                                                   .dotMatchesLineSeparators]) -> NSRegularExpression


func foo(a: Void,
         b: [String: String] =
           [:]) {
}


func foo(data: (size: CGSize,
                identifier: String)) {}

```
Examples of **incorrect** code:
```swift

func validateFunction(_ file: File, kind: SwiftDeclarationKind,
                  ↓dictionary: [String: SourceKitRepresentable]) { }


func validateFunction(_ file: File, kind: SwiftDeclarationKind,
                       ↓dictionary: [String: SourceKitRepresentable]) { }


func validateFunction(_ file: File,
                  ↓kind: SwiftDeclarationKind,
                  ↓dictionary: [String: SourceKitRepresentable]) { }

```

## Further Reading

* [SwiftLint - Vertical Parameter Alignment](https://github.com/realm/SwiftLint/blob/master/Rules.md#vertical-parameter-alignment)