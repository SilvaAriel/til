# Simplified Router
Instead of writing:
```go
router := http.NewServeMux()
router.Handle("/path", http.HandlerFunc(funcHandler))
```
Write:
```go
router := http.NewServeMux()
router.HandleFunc("/path", funcHandler)
```
