## But what if I *want* async operation?

Do it the Go way:

``` go
for _, widget := range widgets {
    go func() {
        output := widget.Frobnicate()
        fmt.Printf("Input = %s, Frobnicated value = %s\n", widget.Value, output)
    }()
}
```
