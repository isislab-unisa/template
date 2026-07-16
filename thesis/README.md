# ISISLab Unified Bachelor/Master Thesis - Overleaf pdfLaTeX Edition

This is one LaTeX project for Bachelor and Master theses at the University of Salerno. It supports complete English/Italian switching and is intentionally built for Overleaf's default **pdfLaTeX** compiler.

## Overleaf quick start

1. Upload this ZIP as a new Overleaf project.
2. Set `main.tex` as the **Main document**.
3. In **Menu -> Compiler**, select **pdfLaTeX**.
4. Click **Recompile**.

No XeLaTeX, LuaLaTeX, shell escape, `minted`, Biber, system fonts, or custom compilation command is required. The bibliography uses standard BibTeX; Overleaf runs the necessary bibliography pass automatically.

## Select degree and language

Open `configuration.tex` and change only these values:

```latex
\providecommand{\ISISDegreeChoice}{master}      % bachelor | master
\providecommand{\ISISLanguageChoice}{italian}  % english  | italian
```

The direct command form is also available:

```latex
\thesisdegree{bachelor}
\thesislanguage{italian}
```

The default build is **Master + Italian**.

Selecting `italian` automatically changes the supplied demo thesis content, cover labels, degree wording, abstract, declaration, acknowledgements, table/list names, captions, bibliography title, appendix labels, running headers, and PDF metadata. Short custom bilingual passages can use:

```latex
\LangText{English text}{Testo italiano}
```

Degree-dependent passages can use:

```latex
\IfBachelorTF{Bachelor content}{Master content}
```

## Edit thesis information

Edit `metadata.tex` to set:

- thesis title and subtitle;
- degree course and department;
- candidate name and student ID;
- supervisor and co-supervisor;
- academic year, keywords, and ISISLab information.

The file contains separate metadata blocks for Bachelor/Master and English/Italian builds, so one project can retain all four configurations.

## Bibliography

Add entries to `references.bib` and cite them using normal commands such as:

```latex
\cite{goodfellow2016deep}
```

The template uses the standard `IEEEtran` BibTeX style. Overleaf's normal **Recompile** action handles the required sequence. For a local manual build, use:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

## Optional convenience entry points

The four `variant-*.tex` files compile the same unified project without editing `configuration.tex`:

- `variant-bachelor-english.tex`
- `variant-bachelor-italian.tex`
- `variant-master-english.tex`
- `variant-master-italian.tex`

Set one of them as Overleaf's Main document only when a fixed preview configuration is useful. For normal thesis writing, keep `main.tex` as the Main document.

## Project structure

- `main.tex` - main Overleaf entry point;
- `configuration.tex` - degree, language, and accent switches;
- `metadata.tex` - thesis and student information;
- `isislab-thesis.sty` - modern visual system and automatic selectors;
- `content/bachelor/` - Bachelor demo chapters in English and Italian;
- `content/master/` - Master demo chapters in English and Italian;
- `assets/` - UniSA and ISISLab logos;
- `references.bib` - BibTeX database;
- `demo-pdfs/` - four compiled previews.

## Submission note

Before submitting, verify the official cover wording, declarations, degree-course name, roles, and formatting requirements against the current University of Salerno and degree-programme rules.
