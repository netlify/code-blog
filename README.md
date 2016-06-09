# code.netlify

## Getting Started

[Download Hugo](http://www.gohugo.io/) or:

```bash
$ brew update && brew install hugo
```

## Start Server
```bash
# start server
$ hugo server --theme=hugo-zen --buildDrafts --watch
```

## Create a new post

```bash
$ hugo new post/new-thing.md
```

## Syntax Hylighting

Syntax highlighting is being set in the `config.toml` and the overall
style can be changed using the example color codes from [pygments-css](https://github.com/richleland/pygments-css).

```
# config.toml

pygmentsuseclasses = false
pygmentsstyle = "emacs"
```

example in markdown:

```
{{< highlight js >}}
    function foo() => {
      return 12;
    }
{{< /highlight >}}
```

Theme configuration is [hugo-zen](https://gohugo.io/overview/configuration/)
