Pattern: Use of `(*testing.T).Fatal` from non-test goroutine

Issue: -

## Description

Functions that abruptly terminate a test, such as the Fatal, Fatalf, FailNow, and Skip{,f,Now} methods of `*testing.T`, must be called from the test goroutine itself. This checker detects calls to these functions that occur within a goroutine started by the test. For example:

```go
func TestFoo(t *testing.T) {
    go func() {
        t.Fatal("oops") // error: (*T).Fatal called from non-test goroutine
    }()
}
```


## Further Reading

* [Go Vet - testinggoroutine](https://golang.org/cmd/vet/)
