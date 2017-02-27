Pattern: Incorrect uses of range loop variables in closures

Issue: -

## Description

This rule checks range loop variables bound inside function literals that are deferred or launched in new goroutines. It's likely that this behavior was not intended. Consider the following code:

```go
values := []string{"a", "b", "c"}
for _, v := range values {
	go func() {
		fmt.Println(v)
		done <- true
	}()
}
```
One might mistakenly expect to see `a, b, c` as the output. What you'll probably see instead is `c, c, c`. This is because each iteration of the loop uses the same instance of the variable `v`, so each closure shares that single variable. When the closure runs, it prints the value of `v` at the time `fmt.Println` is executed, but `v` may have been modified since the goroutine was launched.


To bind the current value of `v` to each closure as it is launched, one must modify the inner loop to create a new variable each iteration. One way is to pass the variable as an argument to the closure:

```go
for _, v := range values {
	go func(u string) {
		fmt.Println(u)
		done <- true
	}(v)
}
```

In this example, the value of `v` is passed as an argument to the anonymous function. That value is then accessible inside the function as the variable `u`.

## Further Reading

* [Go - What happens with closures running as goroutines?](https://golang.org/doc/faq#closures_and_goroutines)
* [Go Vet - rangeloops](https://golang.org/cmd/vet/#hdr-Range_loop_variables)
