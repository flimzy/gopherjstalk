# Using field tags

A poorly documented, but powerful feature, is the use of Go's tags in struct definitions. 

``` go
type Pet struct {
    js.Object
    Name string `js:"name"`
}
```

This ties the Go struct element **Name** to the underlying JavaScript object's key **name**. This is useful for:

- No Getters or Setters

- Automatic Type conversions

- Change spelling or case (public vs. private attributes)
