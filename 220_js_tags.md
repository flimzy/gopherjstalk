# Using field tags

A poorly documented, but powerful feature, is the use of Go's tags in struct definitions. 

``` go
type Pet struct {
    js.Object
    Name string `js:"name"`
}
```

This ties the Go struct element **Name** to the underlying JavaScript object's key **name**. This is useful for:

- Allows direct access to the JS key as a native Go variable, avoiding the need to call **.Get()** and **.Set()**
- Handles type conversion automatically, without the need to call a type method such as **.String()** 
- Exporting names of lowercase JS keys (since Go only exports names that start with a capital letter), or vice versa
- a **js.Object** must be embedded in the struct, and it must be explicitly defined in a constructor method. (i.e. the zero value isn't useful--this may be fixed in the future)
