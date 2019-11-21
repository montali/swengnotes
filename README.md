# Riassunti di Ingegneria del Software
>By the way, ALL software projects are done by iterative prototyping.
>Some companies call their prototypes "releases", that's all.

Riassunti per gli esami teorici del corso di Ingegneria del Software, prof. Poggi, A.A. 2019-20.
Qualunque correzione/aggiunta è super ben accetta. Per farlo, forkate il progetto, fate le modifiche necessarie, e aprite una pull request.
Grazie!

## Sans Forgetica
Per ogni file vi è anche una versione realizzata con il font [Sans Forgetica](https://sansforgetica.rmit/), dategli una chance. NB: per motivi implementativi, qui manca il glossario.

## Compilazione
Siccome questi riassunti utilizzano il package `glossaries`, è necessario compilare il tex con:
```
pdflatex teoria.tex
makeglossaries teoria.tex
pdflatex teoria.tex
pdflatex teoria.tex
```

Se utilizzate Latex Workshop per VSCode basta inserire queste due rule nel settings.json di VSCode
```json
    "latex-workshop.latex.recipes": [
        {
          "name": "latexmk 🔃",
          "tools": [
            "latexmk"
          ]
        },
        {
          "name": "latexmk (latexmkrc)",
          "tools": [
            "latexmk_rconly"
          ]
        },
        {
          "name": "latexmk (lualatex)",
          "tools": [
            "lualatexmk"
          ]
        },
        {
          "name": "pdflatex ➞ bibtex ➞ pdflatex × 2",
          "tools": [
            "pdflatex",
            "bibtex",
            "pdflatex",
            "pdflatex"
          ]
        },        
        {
            "name": "pdflatex ➞ glossaries ➞ pdflatex × 2",
            "tools": [
              "pdflatex",
              "makeglossaries",
              "pdflatex",
              "pdflatex"
            ]
          }
      ],
      "latex-workshop.latex.tools": [
        {
          "name": "latexmk",
          "command": "latexmk",
          "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "-pdf",
            "-outdir=%OUTDIR%",
            "%DOC%"
          ],
          "env": {}
        },
        {
          "name": "lualatexmk",
          "command": "latexmk",
          "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "-lualatex",
            "-outdir=%OUTDIR%",
            "%DOC%"
          ],
          "env": {}
        },
        {
          "name": "latexmk_rconly",
          "command": "latexmk",
          "args": [
            "%DOC%"
          ],
          "env": {}
        },
        {
          "name": "pdflatex",
          "command": "pdflatex",
          "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "%DOC%"
          ],
          "env": {}
        },
        {
          "name": "bibtex",
          "command": "bibtex",
          "args": [
            "%DOCFILE%"
          ],
          "env": {}
        },
        {
            "name": "makeglossaries",
            "command": "makeglossaries",
            "args": [
              "%DOCFILE%"
            ],
            "env": {}
          }
      ]
```
