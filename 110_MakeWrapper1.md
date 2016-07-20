# Calling Go code from JavaScript

A standard Go struct, with getter and setter:

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
