| Go type               | JavaScript type       | Conversions back to interface{} |
| --------------------- | --------------------- | ------------------------------- |
| bool                  | Boolean               | bool                            |
| integers and floats   | Number                | float64                         |
| string                | String                | string                          |
| []int8                | Int8Array             | []int8                          |
| []int16               | Int16Array            | []int16                         |
| []int32, []int        | Int32Array            | []int                           |
| []uint8               | Uint8Array            | []uint8                         |
| []uint16              | Uint16Array           | []uint16                        |
| []uint32, []uint      | Uint32Array           | []uint                          |
| []float32             | Float32Array          | []float32                       |
| []float64             | Float64Array          | []float64                       |
| all other slices      | Array                 | []interface{}                   |
| arrays                | see slice type        | see slice type                  |
| functions             | Function              | func(...interface{}) *js.Object |
| time.Time             | Date                  | time.Time                       |
| -                     | instanceof Node       | *js.Object                      |
| maps, structs         | instanceof Object     | map[string]interface{}          |
