# Go bindings for JS code

It is possible to make direct calls to all JS libraries, but bindings are easier.

Best practice is to write a very minimal binding layer around a JavaScript library:

``` go
package frobbinding

import "github.com/gopherjs/gopherjs/js"

type Widget struct {
    js.Object
    Value string `js:"value"`
}

func New(value string) *Widget { // Constructor wrapper
    // var w = new Object;
    w := js.Global.Get("Object").New()
    // w.value = value;
    w.Value = value
    // return w
    return w
}

func (w *Widget) Frobnicate(args ...interface{}) {
    // w.frobnicate(args1, arg2, arg3, .. argN);
    w.Call("frobnicate", args...) // Async func with variable number/type of arguments
}
```
