# reviewer

Get beautiful reviewer presentations from your Markdown files.
Supports Emoji & Check Box - Hurray

## Installation

``` bash
npm install -g reviewer
```

## Markdown in reviewer

The Markdown feature of reviewer is awesome, and has an easy (and configurable) syntax to separate slides.
Use three dashes surrounded by two blank lines (`\n---\n`).
Example:

``` text
# Title

* Point 1
* Point 2

---

## Second slide

> Best quote ever.


```

The separator syntax can be overriden (e.g. I like to use three blank lines).

## Speaker Notes

You can use the [speaker notes](https://github.com/hakimel/reviewer#speaker-notes) feature by using a line starting with `Note:`.


## Usage

To open specific Markdown file as reviewer slideshow:

``` bash
reviewer slides.md
```

You can also provide a url that resolves to a Markdown resource (over http(s)).

``` bash
reviewer https://raw.github.com/webpro/reviewer/master/demo/a.md
```

Show (recursive) directory listing of Markdown files:

``` bash
reviewer dir/
```

Show directory listing of Markdown files in current directory:

``` bash
reviewer
```

Override theme (default: `black`):

``` bash
reviewer slides.md --theme solarized
```

Override reveal theme with a custom one:

``` bash
# you'll need a theme/my-custom.css file
reviewer slides.md --theme my-custom
```

Override [highlight theme](https://github.com/isagalaev/highlight.js/tree/master/src/styles) (default: `zenburn`):

``` bash
reviewer slides.md --highlightTheme github
```

Override slide separator (default: `\n---\n`):

``` bash
reviewer slides.md --separator "^\n\n\n"
```

Override vertical/nested slide separator (default: `\n----\n`):

``` bash
reviewer slides.md --vertical "^\n\n"
```

Override port (default: `1948`):

``` bash
reviewer slides.md --port 8888
```

Disable to automatically open your web browser:

``` bash
reviewer slides.md --disableAutoOpen
```

## Print Support

*Requires phantomjs to be installed (preferably globally)*

This will try to create a pdf with the passed in file (eg slides.md) and outputted to the name passed into the `--print` parameter (eg slides.pdf)

``` bash
reviewer slides.md --print slides.pdf
```

## Options

You can define reviewer [options](https://github.com/hakimel/reviewer#configuration) in a `revieweron` file that you should put in the root directory of the Markdown files. They'll be picked up automatically. Example:

``` json
{
    "controls": true,
    "progress": true
}
```

## Notes

* `reviewer` always starts a local server and opens the default browser
* From any presentation, navigate to the root (e.g. [http://localhost:1948](http://localhost:1948)) to get directory listing of (linked) Markdown files. Root folder is resolved from Markdown file (or directory) `reviewer` was started with.

## Reference

* Forked From [reveal-md] (https://github.com/webpro/reveal-md.git)

## Development 
Update package.json
``` bash
npm uninstall -g reviewer
npm publish
npm install -g reviewer
```

* Testing Locally
npm pack
npm install (tar-file)

[Link](http://podefr.tumblr.com/post/30488475488/locally-test-your-npm-modules-without-publishing)