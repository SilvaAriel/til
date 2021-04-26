Instead of testing JSON string, parse it into a Data Structure instead, because debugging string differences can be really trick.

json.NewDecoder() takes a io.Reader, so it can use a Handler's `http.ResponseWriter`

Example:
```go
import "encoding/json"

type Player struct {
  Name  string
  Wins  int
}
var got []Player
err := json.NewDecoder(response.Body).Decode(&got)
```
