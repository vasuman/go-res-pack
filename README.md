# go-res-pack

A tool that packages resource files (templates and stylesheets) with
your Go app.

## Usage

Resources get their own package. Within this package have a
directory(`<data-dir>`) in which the files are stored.

Create a _stub_ Golang file in the package which contains.

```go

//go:generate go-res-pack <data-dir> <out-file>

func Setup() {
    genInit()
}
```

First, you've got to `go get github.com/vasuman/go-res-pack`.

Then run a `go generate` on the package.

Before any of its members are accessed, the `Setup` function needs to
be called.

Then you can access,

* Template - `Template`
* Styles - `Styles`
