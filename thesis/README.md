# ISISLab Unified Thesis Template 
A single pdfLaTeX project for Bachelor and Master theses, with automatic English/Italian content selection and an ISISLab visual identity.

## Overleaf quick start

1. Upload this ZIP as a new Overleaf project.
2. Keep `main.tex` as the Main document.
3. Select **pdfLaTeX** as the compiler.
4. Click **Recompile**.

The project uses the normal Overleaf build process. It contains no `.latexmkrc`, custom compiler command, shell escape, external fonts, or generated graphics.

## Select degree and language

Edit only these two lines in `configuration.tex`:

```latex
\providecommand{\ISISDegreeChoice}{master}      % bachelor | master
\providecommand{\ISISLanguageChoice}{italian}  % english  | italian
```

The direct command form remains available:

```latex
\thesisdegree{bachelor}
\thesislanguage{english}
```

## Optional research-writing guide, appendix, and reproducibility checklist

The template-only research-writing chapter, appendix, and checklist are independently optional. Set them in `configuration.tex`:

```latex
\providecommand{\ISISResearchWritingGuideChoice}{enabled}     % enabled | disabled
\providecommand{\ISISAppendixChoice}{enabled}                  % enabled | disabled
\providecommand{\ISISReproducibilityChecklistChoice}{enabled} % enabled | disabled
```

The research-writing chapter is enabled in the demo so that the example pages appear in the compiled PDF. Disable it before turning the project into a final thesis. It adapts Simon Peyton Jones's Microsoft Research guidance to a longer thesis: one central claim, a concrete problem, refutable contributions, claim-to-evidence links, intuition before formal detail, fair related-work positioning, direct language, limitations, and reader feedback.

The selected language automatically loads:

- `content/writing-guide/research-thesis-guide-en.tex` or `research-thesis-guide-it.tex`;
- `content/appendix/appendix-en.tex` or `appendix-it.tex`;
- `content/reproducibility/checklist-en.tex` or `checklist-it.tex`.

The checklist is a thesis-oriented adaptation of the common NeurIPS format: **Yes / No / N/A**, followed by evidence or a short justification. It is explicitly optional, supports non-applicable items, and is not the official NeurIPS submission form. Its item groups cover claims, limitations, theory, reproducibility, code/data access, experimental detail, uncertainty, compute, ethics, impact, safeguards, licences, released artefacts, human participants, institutional review, and material use of generative AI or LLMs.

Recommended order in the PDF is: thesis body, references, optional technical appendix, optional reproducibility checklist. This follows the common conference convention that supporting appendices precede the checklist.

Changing the language selects the matching demo front matter, research-writing example chapter, thesis chapters, appendix example, reproducibility checklist, cover labels, headings, declaration, acknowledgements, bibliography title, and interface text.

The second-page ISISLab research profile is also translated automatically. It contains three concise lines based on the official ISISLab website: the laboratory's UniSA affiliation and founding year, its three main research areas, and its participation in more than 20 national and European projects.

## Why this edition compiles faster

The template was rebuilt to avoid expensive drawing and styling engines. It uses:

- native LaTeX rules, boxes, and KOMA-Script headings;
- lightweight `framed` callouts;
- pre-optimized PNG logos;
- a pre-baked transparent watermark reused as one image object;
- standard BibTeX with the official `ACM-Reference-Format`;
- no runtime chart generation.

The removed heavy components include TikZ, PGFPlots, tcolorbox, minted, Biber, and external font loading. Demo diagrams and charts are built from simple boxes and rules.

On the local verification system, a clean pdfLaTeX pass decreased from about **5.0 seconds** in the previous project to about **2.5 seconds** in this edition. Actual Overleaf times depend on server load and project size.

## Edit thesis metadata

Edit `metadata.tex` to set:

- title and subtitle;
- author and student ID;
- degree course and department;
- supervisor and co-supervisor;
- academic year and keywords;
- ISISLab name and website.

The file keeps separate metadata blocks for Bachelor/Master and English/Italian variants.

## Bibliography

Add entries to `references.bib` and cite them normally:

```latex
\cite{goodfellow2016deep}
```

The bibliography uses the official ACM BibTeX style `ACM-Reference-Format` with lightweight `natbib` numeric, sorted, compressed citations. Overleaf handles it automatically with the normal Recompile button, and citations remain standard `\cite{...}` commands.

## Project structure

- `main.tex` - normal Overleaf entry point;
- `configuration.tex` - degree, language, optional-content switches, and accent selection;
- `metadata.tex` - thesis and student data;
- `isislab-thesis.sty` - lightweight visual system;
- `content/writing-guide/` - optional thesis-writing chapter and example pages in both languages;
- `content/bachelor/` - Bachelor demo content in both languages;
- `content/master/` - Master demo content in both languages;
- `content/appendix/` - optional English/Italian appendix examples;
- `content/reproducibility/` - optional English/Italian reproducibility checklist examples;
- `assets/` - optimized UniSA and ISISLab logos;
- `references.bib` - BibTeX database;
- `variant-*.tex` - optional fixed preview entry points.

## Submission note

Before submission, verify the official University of Salerno cover wording, declarations, degree-course name, roles, and formatting requirements required by the current programme.


## Checklist provenance

The checklist structure is adapted for thesis use from the NeurIPS Paper Checklist Guidelines (`https://neurips.cc/public/guides/PaperChecklist`). It is provided as an editable example, not as an official or complete compliance statement for NeurIPS, KDD, the University of Salerno, or any degree programme. Always verify the current institutional submission rules.


## Research-writing guide provenance

The optional bilingual guide is a thesis-oriented adaptation of Simon Peyton Jones, *How to Write a Great Research Paper*, Microsoft Research. The template paraphrases the principles and does not reproduce the slide deck. See `RESEARCH-WRITING-GUIDE-SOURCE.txt` for the source URL and adaptation notes. University and degree-programme requirements always take precedence.
