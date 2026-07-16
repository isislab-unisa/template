# ISISLab Beamer template

## English demo
Compile the English demo with:

```bash
latexmk -pdf main.tex
```

## Italian labels and demo
The theme now supports localized fixed template labels without changing the visual style.

```latex
\usepackage[italian]{isislabtheme}
```

Accepted aliases are `italian`, `italiano`, and `ita`. The option localizes the built-in template labels such as the agenda name, section divider label, and department badge.

Compile the full Italian demo with:

```bash
latexmk -pdf main_ita.tex
```

`main_ita.tex` mirrors the content and structure of the English demo in Italian.
