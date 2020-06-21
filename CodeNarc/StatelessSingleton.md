Pattern: Stateless singleton

Issue: -

## Description

There is no point in creating a stateless Singleton because there is nothing within the class that needs guarding and no side effects to calling the constructor. Just create new instances of the object or write a Utility class with static methods. In the long term, Singletons can cause strong coupling and hard to change systems.

If the class has any fields at all, other than a self reference, then it is not considered stateless. A self reference is a field of the same type as the enclosing type, or a field named `instance` or `_instance`.

Example of violations:

``` groovy
@groovy.lang.Singleton
class Service {
   // violation: the class has no fields but is marked Singleton
    void processItem(item){
    }
}

class Service {
   // violation: the class has no fields other than 'instance' but is marked Singleton
    static instance
    void processItem(item){
    }
}

class Service {                                       // violation
    static Service service
    void processItem(item){
    }
}
```

## Further Reading

* [CodeNarc - StatelessSingleton](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#statelesssingleton-rule)