![CI](https://github.com/pettni/um-thesis/workflows/ubuntu-latest-apt/badge.svg) ![CI](https://github.com/pettni/um-thesis/workflows/ubuntu-20.04-texlive/badge.svg)

# um-thesis

Template for a Ph.D. thesis at the University of Michigan. The template is based on the Komascript ```scrbook``` class and is intended to be a modern, lightweight, and customizable alternative to the different ```rac.sty```-based classes (the original ```rac.sty``` was created in 1988!). Example of complete thesis: https://deepblue.lib.umich.edu/handle/2027.42/140897.

## Features
 - Follows [Rackham requirements](https://rackham.umich.edu/navigating-your-degree/formatting-guidelines/) (**open an issue or a PR if this is no longer the case**)
 - List of acronyms (```glossaries``` package)
 - List of appendices
 - Clutter-free main files
 - Easy font selection

## Compilation

### Hosted

The template works in [Overleaf](https://www.overleaf.com/) as of November 2018; just set the compiler to ```XeLaTeX``` in the project settings (or remove the ```fontspec``` package and use the default compiler ```pdfLaTeX```). I don't know how ```tikzexternalize``` is handled in these environments, so the ```\tikzexternalize[prefix=figures_compiled/]``` command in ```preamble.tex``` should probably be left disabled. Any custom fonts will also have to be uploaded to overleaf.

### Local

The recommended tex environment is [TexLive](https://tug.org/texlive/) with a new-ish version of ```latexmk``` and ```koma-script``` v3.28 or newer.

 * On Ubuntu 20.04 the latex packages provided in APT work fine. Install all necessary packages via

```
sudo apt-get install texlive-latex-base texlive-xetex latexmk biber
```

 * On Ubuntu 18.04 the latex packages in APT are dated and will not work out of the box. See https://www.tug.org/texlive/acquire-netinstall.html for the manual installation procedure.

 * For a (non-full) TexLive install this commands installs all required CTAN packages

```
tlmgr install koma-script xetex morewrites mathdots booktabs setspace textcase datatool xstring todonotes chngcntr xpatch doublestroke glossaries mfirstuc xfor biblatex biber pgf pgfplots unicode-math lipsum
```

The template can be compiled with latexmk using [settings](http://ctan.mirrors.hoobly.com/support/latexmk/latexmk.pdf) defined in ```latexmkrc```. The default compiler is ```xelatex``` (to use ```pdflatex``` the ```fontspec``` package must be removed in ```preamble.tex```).

```
latexmk
```

Alternatively, use an environment like Sublime Text + [LatexTools](https://latextools.readthedocs.io/en/latest/) or VS Code + [LaTeXWorkshop](https://github.com/James-Yu/LaTeX-Workshop) that uses ```latexmk``` under the hood.


## Configuration

The Koma-Script Bundle is highly customizable, see the [Koma-Script guide](http://texdoc.net/texmf-dist/doc/latex/koma-script/scrguien.pdf) for detailed descriptions.

### Fonts

Fonts are handled with ```fontspec/unicode-math``` and the ```\setmainfont{}``` and ```\setmathfont{}``` commands. For finer control, use the ```\setkomafont{element}``` commands (for a full list of customizable elements, see Chapter 3.6 of the Koma-Script guide). Suggested font collections:

 - Libertinus: https://github.com/libertinus-fonts/libertinus
 - XITS family (no sans): https://github.com/alif-type/xits
 - Linux Libertine/Linux Biolinum (no math)
 - Minion Pro/Myriad Pro/Minion math (non-free)


## Acknowledgment

The title page template is taken from the [thesis-umich.cls](http://www-personal.umich.edu/~dalle/codes/thesis-umich/downloads/thesis-umich.cls) derivation of ```rac.sty```.
