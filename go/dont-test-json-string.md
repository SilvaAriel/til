Instead of testing JSON string, parse it into a Data Structure instead, because debugging string differences can be really trick.

json.NewDecoder() takes a io.Reader, so it can use a Handler's `http.ResponseWriter`

Example:
```go
import (
  "encoding/json"
  "reflect"
)

type Player struct {
  Name  string
  Wins  int
}
want := []Player{"Tsubasa", 5}

var got []Player
err := json.NewDecoder(response.Body).Decode(&got)

if !reflect.DeepEqual(got, want) {
  t.Errorf("Wanted %v, but got %v", want, got)
}
```
