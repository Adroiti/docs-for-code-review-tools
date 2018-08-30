Pattern: Inconsistent modifier order

Issue: -

## Description

Modifier order should be consistent.

Examples of **correct** code:
```swift
public class Foo { 
   public convenience required init() {} 
}


public class Foo { 
   public static let bar = 42 
}


public class Foo { 
   public static var bar: Int { 
       return 42   }}


public class Foo { 
   public class var bar: Int { 
       return 42 
   } 
}


public class Bar { 
   public class var foo: String { 
       return "foo" 
   } 
}
```
Examples of **incorrect** code:
```swift
class Foo { 
   convenience required public init() {} 
}


public class Foo { 
   static public let bar = 42 
}


public class Foo { 
   static public var bar: Int { 
       return 42 
   } 
} 


public class Foo { 
   class public var bar: Int { 
       return 42 
   } 
}


public class RootFoo { 
   class public var foo: String { 
       return "foo" 
   } 
}

```

## Further Reading

* [SwiftLint - Modifier Order](https://github.com/realm/SwiftLint/blob/master/Rules.md#modifier-order)