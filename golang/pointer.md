
# Stack

The stack contains the ongoing variables for a given goroutine. Once a function returned, the variables are popped from the stack.
```
func getFooValue() foo {
	var result foo
	// Do something
	return result
}
```

# Heap

The heap contains the shared variables (global variables, etc.).

The Go compiler will escape variables to a place where the variables can be shared: the heap.
```
func getFooPointer() *foo {
	var result foo
	// Do something
	return &result
}
```

# Passing pointer

Passing pointers, though, is another scenario.
```
func main()  {
	p := &foo{}
	f(p)
}
```

Because we are calling f within the same goroutine, the p variable does not need to be escaped. It is simply pushed to the stack and the sub-function can access it.
For example, this is a direct consequence of receiving a slice in the Read method of io.Reader instead of returning one. Returning a slice (which is a pointer) would have escaped it to the heap.

