# Thesis Template

Ein LaTeX Template für Abschluss- und Hausarbeiten. 

Dieses Template ist **keine** offizielle Vorlage. Es handelt sich lediglich um eine an die [**offizielle Vorlage**](https://www.inb.uni-luebeck.de/mitarbeiter/infos-downloads-abschlussarbeiten.html) angelehnte Variante.

Das Template ist eine für Medieninformatiker:innen angepasste Version der [Vorlage](https://github.com/malteschmitz/latex-thesis) 
von [Malte Schmitz](https://github.com/malteschmitz).<br>
Geändert wurde:
- der Zitationsstil (ist jetzt apa7)
- das Layout der Titelseite (ist jetzt zentriert)
- die maincolor (entspricht jetzt der corporate design Farbe der Uni Lübeck)

Da für Zitationen biblatex verwendet wird, muss der Texteditor evtl. konfiguriert werden. Anleitungen für verschiedene Texteditoren sind 
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