# Calling JavaScript code from Go

The **github.com/gopherjs/gopherjs/js.Object** type provides the fundamental glue between JavaScript objects and Go.

**js.Object** can store any type of JavaScript object. In true JavaScript fashion, it is up to you to use it properly.

``` go

func main() {
    window := js.Global // `window` in the browser, `GLOBAL` for node.js
    div := js.Call("getElementById", "someid")
    fmt.Printf("Inner HTML contains: %s\n", div.Get("innerHTML").String() )
}
```
