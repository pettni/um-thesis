# um-thesis

Template for a Ph.D. thesis at the University of Michigan. The template is based on the Komascript ```scrbook``` class and was created out of frustration with the frequent compilation warnings associated with the different ```rac.sty```-based classes, as well as a desire to work in a flexible and modern latex environment. 

## Compilation
The easiest way to compile is to use latexmk:
```
latexmk -cd -f -pdf -interaction=nonstopmode -synctex=1 um-thesis.tex
```
Alternatively, use an environment like Sublime Text + LatexTools that relies on ```latexmk``` for compilation.

## Features
 - Follows [Rackham requirements](http://www.rackham.umich.edu/content/formatting-dissertation)
 - Todo list (```todonotes``` package)
 - Handling of acronyms (```glossaries``` package) 
 
## Acknowledgement

The title page formatting is taken from the [thesis-umich.cls](http://www-personal.umich.edu/~dalle/codes/thesis-umich/downloads/thesis-umich.cls) derivation of ```rac.sty```.
