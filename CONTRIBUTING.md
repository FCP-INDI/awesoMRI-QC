# Contributing

Your contributions are always welcome!

Seriously, we'd love your help making this a useful resource.

## Guidelines

### Easy way

* Open an issue pointing to the tool/metric/reference/etc you'd like added, or the correction you'd like made. We'll take care of the rest!

### Faster way

* Fork the repository.
* Make your additions to [**README_pandoc.md**](README_pandoc.md) (**VERY IMPORTANT**).
* Update the bib file [mri-qc.bib](mri-qc.bib) if necessary. **Please remember to include a DOI.**
  * Don't worry about the `date-added`, `date-modified`, and `bdsk-*` fields. These are created by [BibDesk](https://bibdesk.sourceforge.io/).
* Run `make build` to compile [README.md](README.md). You will need [pandoc](https://pandoc.org/) for this.
* Commit your changes.
* Open a Pull Request.
* Make sure the PR title is in the format of `Add something-or-other`.
* Tell us why you think we should include your addition. (Very likely we'll approve, but it helps our understanding.)

## VS Code tips

If you install the [Pandoc Citer](https://marketplace.visualstudio.com/items?itemName=notZaki.pandocciter) and [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) extensions and add these to your `settings.json`

```json
{
    "PandocCiter.DefaultBib": "mri-qc.bib",
    "markdown.extension.toc.levels": "2..6"
}
```

it will help with auto-complete citations and automatic table of contents.