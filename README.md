
# Notes

29/08/2019
Ashley Smith
ashley.smith@ed.ac.uk

This template was assembled over time based off my own thesis-writing experience, with various snippets cobbled together from the Overleaf help documentation and Stack Exchange (see links within).

This template uses the "book" document class and aims to make minimal modifications to the default behaviours, along with a recommended (minimal?) set of packages, to produce something that follows the Edinburgh thesis guidelines.

It uses biblatex+biber (instead of natbib) - see https://tex.stackexchange.com/a/25702

I made some complicated setup with the biblatex import (see packages.tex) to get things behaving how I wanted them - this might be a bit fragile!

# Setup

[Overleaf](https://overleaf.com) is the easiest way to start using Latex.

1. Make an account there. Use your institutional email [if your institution is signed up](https://www.overleaf.com/for/universities) - this will give you "Professional" access which I think is required for the direct Mendeley integration (otherwise just upload the .bib file manually each time you update it).

2. Once signed into Overleaf, you can create a new project from [a zip file of this repository](https://github.com/smithara/thesis-template/archive/master.zip) - from the [Projects dashboard](https://www.overleaf.com/project), click ``New Project / Upload Project``.

3. You might then create a copy of the project and rename it to your own project and modify it with your content, keeping the original copy as a reference.

Compilation (building the pdf) is probably slower on Overleaf than your own computer, and could time out if it takes too long (could be 5 minutes?) - in this case you might be using [Texmaker](https://www.xm1math.net/texmaker/). Texmaker does not use biber by default, so change the "Quick Build" button to ``pdflatex %.tex | biber % | pdflatex %.tex | evince %.pdf``


# Useful references

- https://www.overleaf.com/learn
- http://ctan.mines-albi.fr/info/latex-refsheet/LaTeX_RefSheet.pdf
- http://www.latex4ei.de/downloads/LaTeX_CheatSheet.pdf
- https://www.overleaf.com/learn/latex/Management_in_a_large_project
- https://www.overleaf.com/learn/latex/How_to_Write_a_Thesis_in_LaTeX_(Part_1):_Basic_Structure

# Use Mendeley

Use the [Mendeley reference manager](https://www.mendeley.com/) and link it to Overleaf. First remove the example `references.bib` file already in this template. Then in Overleaf: Click Upload (small button at the top left), then "From Mendeley". Follow instructions to login to your Mendeley account and link your new references.bib. Whenever you modify the Mendeley library, make sure it is sync'd to the Mendeley account (click "Sync" in Mendeley), then click on references.bib in Overleaf and click "Refresh".

# Overall structure
```
 ├─ main.tex : frontmatter: {cover, abstract, lay summary, declaration, ackn,
                             contents, figlist, tablist, glossary}
               mainmatter:  {chapters}
               backmatter:  {appendices, bibliography}
                                          [references.bib imported from mendeley]
   inputs:
 |  ├─ packagesetup.tex     [packages used]
 |  ├─ commands.tex         [defining new commands]
   includes:
 |  ├─ glossary.tex
 |  ├─ chapter1/chapter1.tex
 |  ├─ chapter2/chapter2.tex etc.
 |  ├─ appendices/appendix1.tex


Chapters structure:
 |  ├─ /chapter1/
 |     ├─ /figs/
 |        ├─ fig1.png
 |        ├─ fig2.png etc.
 |     ├─ /chapter1.tex
 |  ├─ /chapter2/ etc.

Use \includeonly{chap3/chap3.tex, chap4/chap4.tex} to limit the compilation
  [see lines 76-86]
Select [Fast/draft] in the drop-down menu from [Compile] to compile without images & links

Chapter names:
1) intro/intro.tex    Introduction
2) chap1/chap1.tex    Chapter 1
8) conc/conc.tex      Conclusion
```


# Edinburgh thesis format rules

This template should follow [the thesis format rules for Edinburgh University](https://www.ed.ac.uk/files/atoms/files/thesisbinding.pdf) for two-sided A4 printing. It may be close enough for other institutions, but shouldn't be too hard to modify, e.g.:

- in `packages.tex`, change the line `\usepackage[a4paper,top=2cm,bottom=4cm,inner=4cm,outer=2.5cm,twoside]{geometry}`
- in `main.tex`, change `\documentclass[openright,twoside,a4paper,english,12pt]{book}`

Edinburgh thesis format summary:
```
4cm binding margin
2cm head margin
2.5cm fore-edge margin
4cm tail margin
The text of the thesis submitted to the examiners may be produced double-sided copy or singlesided
copy. In the case of double-sided copy, each chapter must start on a right-facing page and
for single-sided copy on right-facing pages only. The final, published thesis may be produced in
single-sided or double-sided copy. The main text should be in not less than 1.5 spacing (or 18
points leading). Quotations and notes should be in single spacing. Pagination must be continuous
throughout and include all plans, tables, illustrations etc, which are bound in with the text.
Handwritten numbers in indelible ink are acceptable.
Title page
Abstract
Lay summary
Signed declaration
```
