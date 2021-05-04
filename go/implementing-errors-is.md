# Errors.Is() and its customization

Instead of comparing errors using `==`, it's preferable to use `errors.Is()` because it considers all the errors in chain (wrapepd errors).

It's also possible to customize Is() to define what to compare.

Ex.:
```go
type FieldError struct {
	Field string
}

func (e *FieldError) Error() string {
	return fmt.Sprintf("%q is required", e.Field)
}

func (e *FieldError) Is(target error) bool {
	t, ok := target.(*FieldError)
	if !ok {
		return false
	}
	return e.Field == t.Field
}

// Comparing
if !errors.Is(expectedError, errorReturned) {
    t.Errorf("Got error %q, but wanted error %q", errorReturned, expectedError)
}
```

Source: (Working with Errors in Go 1.13)[https://blog.golang.org/go1.13-errors]