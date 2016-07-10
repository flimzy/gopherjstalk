# “Nearly everything is supported, including Goroutines!”

Standard Go libraries are supported except:

 - build, importer, gosym, and a few other things used for compling Go (i.e. who cares?)
 - net/* (partial support), tls
 - os/*, syscall (mostly supported, but in node.js only)
 - runtime (partial support)
 - Timezones other than UTC and Local
 - unsafe
 
In practice, **runtime** and **unsafe** are the only things here that often matter.
