... and avoid variadic functions when possible. Instead create a separate method for each valid variation:

``` go
func (w *Widget) FrobnicateWithTransformation(transform func(string) string) (output string) {
    var wg sync.WaitGroup
    wg.Add(1)
    go func() {
        // Note we're calling the same underlying function, but with different arguments
        w.o.Frobnicate(transform, func(o string) {
            output = o
            wg.Done()
        })
    }()
    wg.Wait()
}
```
