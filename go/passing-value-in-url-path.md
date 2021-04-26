# Passing value in URL path with fmt.Sprintf

`http.NewRequest()` takes a URL of type string. So we can use `fmt.Sprintf()` to build our URL since it returns a string.

```go
country := "brazil"
req, _ := http.NewRequest(http.MethodGet, fmt.Sprintf("/countries/%s", country), nil)
```
