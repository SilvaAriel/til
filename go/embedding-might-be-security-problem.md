Embedding is a great feature in Go but it might hide a security issue if implemented wrongly.

If you embed `http.ServeMux` (concrete type) for example, users will be able to call `Handle(path, handler)` and set new routes. 
