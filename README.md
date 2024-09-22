# MUDS-Graduation-Thesis

This repository distributes templates for graduation theses from the Department of Data Science, Faculty of Data Science, Musashino University.

LaTeX is a software for writing papers and reports.
It has many commands for using mathematical formulas, which is very useful if you use a lot of mathematical formulas.
In addition, compared to Microsoft Word, it works well with Git and is easy to back up using GitHub, etc.

There is still room for improvement in this template. We welcome your pull requests.


## Setup

As we recommend the use of macOS in our department, we will support the setup in macOS here.


### Install Homebrew and Visual-Studio-Code

Skip if you have already installed it.

```shell
# Install Homebrew
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Visual-Studio-Code
$ brew install visual-studio-code --cask
```


### Install mac-tex

```shell
$ brew install mactex-no-gui --cask
$ exec $SHELL -l
```


### Install latex-workshop to Visual-Studio-Code

Install latex-workshop from the url below or from the extension in vscode.

https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop


### Edit `settings.json`

Please add the following to Visual-Studio-Code's `settings.json`

```json
{
  "latex-workshop.latex.tools": [
    {
      "command": "latexmk",
      "args": [
        "-e",
        "$latex=q/platex %O -synctex=1 -interaction=nonstopmode -file-line-error %S/",
        "-e",
        "$bibtex=q/pbibtex %O %B/",
        "-e",
        "$biber=q/biber %O --bblencoding=utf8 -u -U --output_safechars %B/",
        "-e",
        "$makeindex=q/mendex %O -o %D %S/",
        "-e",
        "$dvipdf=q/dvipdfmx %O -o %D %S/",
        "-norc",
        "-pdfdvi",
        "%DOC%"
      ],
      "name": "latexmk"
    }
  ],
  "latex-workshop.latex.recipes": [
    {
      "name": "latexmk (tex to PDF)",
      "tools": ["latexmk"]
    }
  ],
  "latex-workshop.view.pdf.viewer": "tab",
  "latex-workshop.latex.clean.subfolder.enabled": true,
  "latex-workshop.latex.autoClean.run": "onBuilt",
  "latex-workshop.latex.clean.fileTypes": [
    "*.aux",
    "*.bbl",
    "*.blg",
    "*.idx",
    "*.ind",
    "*.lof",
    "*.lot",
    "*.out",
    "*.toc",
    "*.acn",
    "*.acr",
    "*.alg",
    "*.glg",
    "*.glo",
    "*.gls",
    "*.ist",
    "*.fls",
    "*.log",
    "*.fdb_latexmk",
    "*.dvi",
    "*.synctex.gz"
  ]
}
```


## Usage

After editing `graduation_thesis.tex`, you can compile it by clicking the Run button in the upper right corner.

Please refer to the many excellent articles on basic notation.


## Precautions

The templates provided in this repository are personal creations and we are not responsible for any problems that may arise as a result of using these templates.
