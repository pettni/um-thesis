# um-thesis

Template for a Ph.D. thesis at the University of Michigan. The template is based on the Komascript ```scrbook``` class and is intended to be a modern, lightweight, and customizable alternative to the different ```rac.sty```-based classes (the original ```rac.sty``` was created in 1988!). Example of complete thesis: https://deepblue.lib.umich.edu/handle/2027.42/140897.

## Features
 - Follows [Rackham requirements](http://www.rackham.umich.edu/content/formatting-dissertation)
 - List of acronyms (```glossaries``` package)
 - List of appendices
 - Clutter-free main files
 - Easy font selection

## Compilation

### Local

The recommended tex environment is [TexLive](https://tug.org/texlive/). If you don't have the full installation, some packages might have to be installed manually to compile the template:

	tlmgr install xelatex xstring todonotes bezos chngcntr xpatch doublestroke glossaries mfirstuc xfor biblatex tikz pgfplots unicode-math

The template can be compiled with latexmk using [settings](http://ctan.mirrors.hoobly.com/support/latexmk/latexmk.pdf) defined in ```latexmkrc```. The default compiler is ```xelatex``` (to use ```pdflatex``` the ```fontspec``` package must be removed in ```preamble.tex```).

	latexmk um-thesis.tex

Alternatively, use an environment like Sublime Text + LatexTools that relies on ```latexmk``` for compilation.

### Hosted

The template works in [Overleaf](https://www.overleaf.com/) as of November 2018; just set the compiler to ```XeLaTeX``` in the project settings (or remove the ```fontspec``` package and use the default compiler ```pdfLaTeX```). I don't know how ```tikzexternalize``` is handled in these environments, so the ```\tikzexternalize[prefix=figures_compiled/]``` command in ```preamble.tex``` should probably be left disabled. Custom fonts will also have to be uploaded to overleaf.

## Configuration

The Koma-Script Bundle is highly customizable, see the [Koma-Script guide](http://texdoc.net/texmf-dist/doc/latex/koma-script/scrguien.pdf) for detailed descriptions.

### Fonts

Fonts are handled with ```fontspec/unicode-math``` and the ```\setmainfont{}``` and ```\setmathfont{}``` commands. For finer control, use the ```\setkomafont{element}``` commands (for a full list of customizable elements, see Chapter 3.6 of the Koma-Script guide). Suggested font collections:

 - Libertinus: https://github.com/libertinus-fonts/libertinus/releases
 - XITS family (no sans): https://github.com/alif-type/xits
 - Linux Libertine/Linux Bilonium (no math)
 - Minion Pro/Myriad Pro/Minion math (non-free)


## Acknowledgment

The title page template is taken from the [thesis-umich.cls](http://www-personal.umich.edu/~dalle/codes/thesis-umich/downloads/thesis-umich.cls) derivation of ```rac.sty```.
