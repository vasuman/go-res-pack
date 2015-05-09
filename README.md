# go-res-pack

A tool that packages resource files (templates and stylesheets) with
your Go app.

## Usage

Resources get their own package. Within this package have a
directory(`<data-dir>`) in which the files are stored.

Create a _stub_ Golang file in the package which contains.

```go
import (
    _ "github.com/vasuman/go-res-pack"
)

//go:generate go-res-pack <data-dir> <out-file>

func Setup() {
    genInit()
}
```

Before any of its members are accessed, the `Setup` function needs to
be called.

Then you can access,

* Template - `Template`
* Styles - `Styles`
