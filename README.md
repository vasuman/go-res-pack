# go-res-pack #

A tool that packages resource files (templates and stylesheets) with
your Go app.

## Usage ##

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

### Templates ###

Files with the extension `.tmpl` are parsed as templates and can be
accessed using the `Template` variable exposed by the package.

All template files are parsed into a single template.

### Styles ###

Files with the extension `.css` are considered styleshhets and are
avaiable via the `Styles` map that maps the path of the stylesheet -
relative to the `<data-dir>` - to its content.

