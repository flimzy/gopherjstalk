# Some Gotchas

- You must start a new goroutine if you want to use blocking code called from external JavaScript.
- Internally, **int32** (aka **int**) is the most efficient, so use that when possible, instead of **int64**, **int8**, **uint**, etc.
- You cannot use low-level system calls, as in the **runtime** and **unsafe** libraries.
- Browsers can't access the filesystem, or make other syscalls.  Obviously.
- Output files can be very large (multiple megabytes). Minification helps, of course.
- There are still some bugs in GopherJS, but development is quite active.
- Documentation is sparse. Care to contribute?
