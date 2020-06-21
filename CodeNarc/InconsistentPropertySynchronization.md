Pattern: Inconsistent property synchronization

Issue: -

## Description

Class contains similarly-named `get` and `set` methods where the `set` method is synchronized and the `get` method is not, or the `get` method is synchronized and the `set` method is not. This may result in incorrect behavior at runtime, as callers of the `get` and `set` methods will not necessarily see a consistent state for the object. The `get` and `set` method should both be synchronized or neither should be synchronized.

Example of violations:

``` groovy
class Person {
    String name
    Date birthday
    boolean deceased
    boolean parent
    int weight

    synchronized setName(String name) {
        this.name = name
    }
    // violation, get method should be synchronized
    String getName() {
        name
    }

    // violation, set method should be synchronized
    void setBirthday(Date birthday) {
        this.birthday = birthday
    }

    synchronized String getBirthday() {
        birthday
    }

    // violation, set method should be synchronized
    void setDeceased(boolean deceased) {
        this.deceased = deceased
    }

    synchronized boolean isDeceased() {
        deceased
    }

    synchronized void setParent(boolean parent) {
        this.parent = parent
    }

    // violation, get method should be synchronized
    boolean isParent() {
        parent
    }

    // violation get method should be synchronized
    @groovy.transform.Synchronized
    void setWeight(int value) {
        weight = value
    }
}
```

## Further Reading

* [CodeNarc - InconsistentPropertySynchronization](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#inconsistentpropertysynchronization-rule)