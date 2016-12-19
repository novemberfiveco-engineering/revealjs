# RevealJS themes for November Five slidedecks

Generate RevealJS based slidedecks by writing Markdown and exporting to HTML sites.

Pandoc can also generate a multitude of other formats (like `docx`, `pdf`, etc)
Works very well for me, hope it does to same for you...

## Installation

I use Sublime Text to do almost all of my editing

    brew cask install sublime-text

Install pandoc, it's a CLI app, so break out your Terminal

    brew install pandoc

Add plugins to work with markdown and pandoc

    + [Markdown](https://packagecontrol.io/packages/MarkdownEditing)
    + [Pandoc](https://packagecontrol.io/packages/Pandoc)

My Pandoc settings in sublime `Sublime Text > Preferences > Package settings > Pandoc > Settings (User)`

    {
      "default": {
        "pandoc-path": "/usr/local/bin/pandoc",
        "transformations": {
          "html": {
            "new-buffer": 0,
            "scope": {
              "text.html": "html",
              "text.html.markdown": "markdown"
            },
            "out-ext": "html",
            "pandoc-arguments": [
              "-t",
              "html5",
              "--template=/Users/stijn/frontend/revealjs/nf-revealjs.html",
              "--section-divs",
              "-o",
              "/tmp/slides.html"
            ]
          },
          "pdf": {
            "scope": {
              "text.html": "html",
              "text.html.markdown": "markdown"
            },
            "pandoc-arguments": [
              "-t",
              "pdf",
              "--latex-engine=/Library/TeX/texbin/pdflatex"
            ]
          },
          "docx": {
            "scope": {
              "text.html": "html",
              "text.html.markdown": "markdown"
            },
            "pandoc-arguments": [
              "-t",
              "docx"
            ]
          },
          "wiki": {
            "new-buffer": 1,
            "scope": {
              "text.html": "html",
              "text.html.markdown": "markdown"
            },
            "out-ext": "wiki",
            "pandoc-arguments": [
              "-t",
              "mediawiki"
            ]
          },
          "slides": {
            "scope": {
              "text.html": "html",
              "text.html.markdown": "markdown"
            },
            "out-ext": "pdf",
            "pandoc-arguments": [
              "-t",
              "beamer",
              "--latex-engine=/Library/TeX/texbin/pdflatex"
            ]
          }
        },
        "pandoc-format-file": [
          "docx",
          "epub",
          "pdf",
          "odt",
          "beamer",
          "html5"
        ]
      }
    }

Find and replace `/Users/stijn/frontend/revealjs/` with the path you are cloning this repository into.

Happy editing...