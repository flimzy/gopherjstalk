# Go bindings for JS code

Bindings are easier than direct calls to JS libraries.

``` go
type Widget struct {
    js.Object
    Value string `js:"value"`
}

func New(value string) *Widget { // Constructor wrapper
    // var o = new Object;
    o := js.Global.Get("Object").New()
    // o.value = value;
    w := &Widget{Object: o, Value: value}
    return w
}

func (w *Widget) Frobnicate(args ...interface{}) {
    // w.frobnicate(args1, arg2, arg3, .. argN);
    w.Call("frobnicate", args...) // Async func with variable number/type of arguments
}
```
