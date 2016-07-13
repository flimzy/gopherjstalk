... with an idiomatic Go layer on top of that:

``` go
type Widget struct {
    o frobbinding.Widget
}

func (w *Widget) Frobnicate() (output string) {
    var wg sync.WaitGroup
    wg.Add(1)
    go func() {
        // w.frobnicate(function(o) {
        //     output = o;
        // });
        w.o.Frobnicate(func(o string) {
            output = o
            wg.Done()
        })
    }()
    wg.Wait()
}
```
