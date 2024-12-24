documentclass: scrbook
classoption:
    - oneside
    - BCOR = 0 pt
    - singlespacing = true 
    - numbers = noenddot
mainfont: TeXGyreTermes
mainfontoptions:
- Path=fonts/
- Extension=.otf
- UprightFont=*-regular
- BoldFont=*-bold
- ItalicFont=*-italic
- BoldItalicFont=*-BoldItalic
fontsize: 12pt
papersize: letter
geometry: "top=1in, left=1.5in, right=1in, bottom=1in, truedimen, twoside=false, bindingoffset=0pt, nohead"
lang: en
author: \yourname
date: \yourdate
title: \yourtitle
subtitle: \yoursubtitle
institute: Augusta University
biblatexoptions:
    - backend=biber
    - style=apa
bibliography: ./references/references.bib
link-citations: true
suppress-bibliography: true
