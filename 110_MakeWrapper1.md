# Calling Go code from Javascript

**MakeWrapper()** allows a Go struct:

``` go
type Pet struct {
    name string
}

func (p *Pet) Name() string {
    return p.name
}

func (p *Pet) SetName(name string) {
    p.name = name
}
```
