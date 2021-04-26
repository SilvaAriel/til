# Writing the minimum amount of code in TDD is good

Writing the minimum amount of code in TDD is a reminder of the things I'm not testing.

Example:

If I'm testing this function:

```go
func Handler(w http.ResponseWriter, r *http.Request) {
  return nil
}
```

I'm only testing if the router exists, but I know I'm not testing its reponse code, return body, headers, etc.
