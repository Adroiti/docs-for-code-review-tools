Pattern: Use of double-brace initialization

Issue: -

## Description

Double-brace initialization can be considered as an anti-pattern, as it unnecessarily creates subclasses and also might break `equals` checks that most often consider instances to be non-equal if the class is not the same to ensure symmetric behavior of the `equals` method as required by its contract.

## Examples

```java
// will fail
List<?> list = new ArrayList<Object>() {
    {
        add(null);
    }
};
// will fail
list = new ArrayList<Object>() {
    {
        add(null);
    }
    {
        add(null);
    }
};
// will fail
list = new ArrayList<Object>() {
    // foo
    {
        add(null);
    }
};
// will fail
list = new ArrayList<Object>() {
    {
        add(null);
    } // foo
};
// will fail
list = new ArrayList<Object>() {
    {
        add(null);
    }
    // foo
};
// will fail
list = new ArrayList<Object>() {
    /* foo */
    {
        add(null);
    }
};
// will fail
list = new ArrayList<Object>() {
    {
        add(null);
    }
    /* foo */
};
// will fail
list = new ArrayList<Object>() {
    {
        add(null);
    } /* foo */
};
// will not fail
list = new ArrayList<Object>() {
    {
        add(null);
    }

    public void foo() {
    }
};
// will not fail
list = new ArrayList<Object>() {
    private Object o;
    {
        add(null);
    }
};
```

## Further Reading

* [checkstyle - AvoidDoubleBraceInitialization](https://checkstyle.sourceforge.io/checks/coding/avoiddoublebraceinitialization.html#AvoidDoubleBraceInitialization)