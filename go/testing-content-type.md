# Testing Content-type

It's pretty simple to test Content Type in Go.

```go
const jsonContentType = "application/json"

func Handler (w http.ResponseWriter, r *http.Request) {
  w.Header().Set("content-type", jsonContentType")
  return nil
}

// Test
want := "application/json"
got := response.Result().Header.Get("content-type")
if got != want {
  t.Errorf("Expected %s content-type, but got %v", want, got)
}

```
