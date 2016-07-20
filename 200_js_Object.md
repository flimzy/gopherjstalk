# Calling JavaScript code from Go

**js.Object** provides the glue between JavaScript objects and Go. It represents a JavaScript object of any type. It is up to you to use it properly.

``` go
func main() {
    window := js.Global /* `window` in the browser, `GLOBAL` for node.js */
    // var div = window.getElementById("someid");
    div := js.Call("getElementById", "someid")
    // console.log("Inner HTML contains: %s\n", div.innerHTML());
    fmt.Printf("Inner HTML contains: %s\n", div.Get("innerHTML").String() )
}
```
