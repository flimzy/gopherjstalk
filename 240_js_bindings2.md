... with an idiomatic Go-style abstraction layer on top of that:

``` go
package frobnicate

import (
    "sync"

    "github.com/gopherjs/gopherjs/js"
    "github.com/frobnicater/frobbinding"
)

type Widget struct {
    o frobbinding.Widget
}

func (w *Widget) Frobnicate() (output string) {
    var wg sync.WaitGroup
    wg.Add(1)
    go func() {
        w.o.Frobnicate(func(o string) {
            output = o
            wg.Done()
        })
    }()
    wg.Wait()
}

```
