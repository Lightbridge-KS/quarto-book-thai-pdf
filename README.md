# Quarto Book in Thai Language with PDF

> This repo demonstrate how to use **Thai language 🇹🇭** in a **[Quarto](https://quarto.org) Book** that render to **PDF**. 

## Introduction

Quarto book in Thai language can be rendered to MS Word or HTML format out of the box, but PDF requires some setup. I'll show you how to do that in this tutorial.

The key is to include thai language setting in the LaTeX preamble of the Quarto book.

## Example

These are the output of this repo: 

-   [**PDF Book in Thai**](./docs/Quarto-Book-ภาษาไทย.pdf) (and [LaTeX output](Quarto-Book-ภาษาไทย.tex))
-   **HTML Book**


## Step 1: Get Thai LaTeX Preamble Setting

If you use `R`, [`{thaipdf}`](https://lightbridge-ks.github.io/thaipdf/) R package can automate this process.

Simply call the following function in your book project.

```r
# install.packages("thaipdf")
thaipdf::use_thai_preamble()
```

It will create [`thai-preamble.tex`](thai-preamble.tex) in your project, which is a LaTeX preamble that enable Thai language type-setting with Thai font default to [TH Sarabun New](https://www.f0nt.com/release/th-sarabun-new/) (please check that this font is installed)



## Step 2: Include Thai Preamble

In the Quarto config (`_quarto.yml` or `_metadata.yml`), add `thai-preamble.tex` to [include in the LaTeX preamble](https://quarto.org/docs/output-formats/pdf-basics.html#latex-includes) in the `pdf` format, like so.

[**_quarto.yml**](./_quarto.yml)

```yml
format:
  pdf:
    include-in-header: "thai-preamble.tex"
```

(You can also keep intermediate LaTeX for debug with `keep-tex: true`)

This book is now ready to be rendered as PDF with Thai font.

It's done!






