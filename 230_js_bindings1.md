# Go bindings for JS code

It is possible to make direct calls to all JS libraries, but the greatest benefit is had by using bindings.

Best practice is to write a very minimal binding layer around a JavaScript library:

``` go
package frobbinding

import "github.com/gopherjs/gopherjs/js"

type Widget struct {
    js.Object
    Value string `js:"value"`
}

func New(value string) *Widget { // Constructor wrapper
    w := js.Global.Get("Object").New()
    w.Value = value
    return w
}

func (w *Widget) Frobnicate(args ...interface{}) {
    w.Call("frobnicate", args...) // An async callback with variable number/type of arguments
}
```
