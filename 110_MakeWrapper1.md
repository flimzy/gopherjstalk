# Calling Go code from Javascript

A standard Go struct:

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
