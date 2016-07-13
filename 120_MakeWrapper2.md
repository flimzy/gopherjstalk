... can be treated as a standard JS object with **MakeWrapper()**:

``` go
func main() {
    js.Global.Set("pet", map[string]interface{}{
        "New": New,
    })
}

func New(name string) *js.Object {
    return js.MakeWrapper(&Pet{name})
}
```
