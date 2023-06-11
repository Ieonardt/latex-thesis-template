# Thesis Template

Ein LaTeX Template für Abschluss- und Hausarbeiten. Angelehnt an die offizielle Vorlage der Universität zu Lübeck für MINT Fächer.

Dieses Template ist **keine** offizielle Vorlage. Es handelt sich lediglich um eine abgewandelte Version der [**offizielle Vorlage**](https://www.inb.uni-luebeck.de/mitarbeiter/infos-downloads-abschlussarbeiten.html).

Da für Zitationen biblatex verwendet wird, muss der Editor konfiguriert werden. Anleitungen für verschiedene Editoren sind 
[hier](https://tex.stackexchange.com/questions/154751/biblatex-with-biber-configuring-my-editor-to-avoid-undefined-citations) zu finden.

Für VSCode folgenden Code in die settings.json einfügen:
```
"latex-workshop.intellisense.citation.backend": "biblatex",
    "latex-workshop.latex.recipes": [
        {
            "name": "xelatex -> biber -> xelatex*2",
            "tools": [
                "xelatex",
                "biber",
                "xelatex",
                "xelatex"
            ]
        },      
    ],
    "latex-workshop.latex.tools": [
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ]
        },
        {
            "name": "biber",
            "command": "biber",
            "args": [
                "%DOCFILE%"
            ]
        },
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        }
    ]
```