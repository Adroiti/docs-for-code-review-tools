Pattern: `this` reference escapes constructor

Issue: -

## Description

Reports constructors passing the `this` reference to other methods. This equals exposing a half-baked objects and can lead to race conditions during initialization.

Example of violations:

``` groovy
class EventListener {
    EventListener(EventPublisher publisher) {
        publisher.register(this)            
        new WorkThread(publisher, this).start()
        new AnotherWorkThread(listener: this)
    }    
}
```

## Further Reading

* [SlideShare - Java Concurrency Gotchas](https://www.slideshare.net/alexmiller/java-concurrency-gotchas-3666977/38)
* [IBM developerWorks - Safe construction techniques](https://www.ibm.com/developerworks/java/library/j-jtp0618/index.html)
* [CodeNarc - ThisReferenceEscapesConstructor](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#ThisReferenceEscapesConstructor)