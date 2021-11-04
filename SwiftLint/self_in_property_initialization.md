Pattern: Use of `self` in property initialization

Issue: -

## Description

`self` refers to the unapplied `NSObject.self()` method, which is likely not expected. Make the variable `lazy` to be able to refer to the current instance or use `ClassName.self`.

Examples of **correct** code:

```swift
class View: UIView {
    let button: UIButton = {
        return UIButton()
    }()
}

class View: UIView {
    lazy var button: UIButton = {
        let button = UIButton()
        button.addTarget(self, action: #selector(didTapButton), for: .touchUpInside)
        return button
    }()
}

class View: UIView {
    var button: UIButton = {
        let button = UIButton()
        button.addTarget(otherObject, action: #selector(didTapButton), for: .touchUpInside)
        return button
    }()
}

class View: UIView {
    private let collectionView: UICollectionView = {
        let layout = UICollectionViewFlowLayout()
        let collectionView = UICollectionView(frame: .zero, collectionViewLayout: layout)
        collectionView.registerReusable(Cell.self)

        return collectionView
    }()
}
```

Examples of **incorrect** code:

```swift
class View: UIView {
    ↓var button: UIButton = {
        let button = UIButton()
        button.addTarget(self, action: #selector(didTapButton), for: .touchUpInside)
        return button
    }()
}

class View: UIView {
    ↓let button: UIButton = {
        let button = UIButton()
        button.addTarget(self, action: #selector(didTapButton), for: .touchUpInside)
        return button
    }()
}

```

## Further Reading

* [SwiftLint - Self in Property Initialization](https://realm.github.io/SwiftLint/self_in_property_initialization.html)