
# Notes

29/08/2019
Ashley Smith
ashley.smith@ed.ac.uk

This template uses the "book" document class and aims to make minimal modifications to the default behaviours, along with a recommended (minimal?) set of packages, to produce something that follows the Edinburgh thesis guidelines.

It uses biblatex+biber (instead of natbib) - see https://tex.stackexchange.com/a/25702

I made some complicated setup with the biblatex import (see packages.tex) to get things behaving how I wanted them - this might be a bit fragile!


# Useful references

https://www.overleaf.com/learn
http://ctan.mines-albi.fr/info/latex-refsheet/LaTeX_RefSheet.pdf
http://www.latex4ei.de/downloads/LaTeX_CheatSheet.pdf
https://www.overleaf.com/learn/latex/Management_in_a_large_project
https://www.overleaf.com/learn/latex/How_to_Write_a_Thesis_in_LaTeX_(Part_1):_Basic_Structure

# Use Mendeley

Use the Mendeley reference manager and link it here. First remove the example references.bib file in this template. Then in Overleaf: Click Upload (small button at the top left), then "From Mendeley". Follow instructions to login to your Mendeley account and link your new references.bib. Whenever you modify the Mendeley library, make sure it is sync'd to the Mendeley account (click "Sync" in Mendeley), then click on references.bib in Overleaf and click "Refresh".

# Overall structure

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



# Edinburgh thesis format rules

Ed Thesis Format: https://www.ed.ac.uk/files/atoms/files/thesisbinding.pdf

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



# (UN)LICENSE

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org/>