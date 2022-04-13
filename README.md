### What's the differences from official flag

- add `SkipOnError` strategy, which just skip and continue to parse next flags, neither exit nor panic.

```go
const (
	ContinueOnError ErrorHandling = iota // Return a descriptive error.
	SkipOnError                          // Skip and continue
	ExitOnError                          // Call os.Exit(2) or for -h/-help Exit(0).
	PanicOnError                         // Call panic with a descriptive error.
)
```

- Enable `SkipOnError` strategy by default.

```go
var CommandLine = NewFlagSet(os.Args[0], SkipOnError)
```
