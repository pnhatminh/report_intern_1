# LaTeX project structure

`main.tex` is the document entry point. It only loads configuration and content modules.

- `config/`: packages, typography, numbering, links, and shared commands.
- `frontmatter/`: cover page, declaration, acknowledgements, summary, and lists.
- `chapters/`: one source file per report chapter.
- `tables/`: one file per table or longtable; `result-table-commands.tex` contains shared result-table wrappers.
- `figures/`: LaTeX figure wrappers and generated plots.
- `assets/images/`: raster image assets used by figures.
- `backmatter/`: appendices and bibliography commands.
- `references/references.bib`: BibTeX database.
- `references/*.pdf`: source standards and internal reference documents.

Compile from the repository root so all `\input` and image paths resolve correctly:

```sh
latexmk -xelatex -interaction=nonstopmode -outdir=build main.tex
```

When adding content:

1. Put chapter prose in the relevant file under `chapters/`.
2. Put each new table in `tables/` and include it with `\input{tables/<name>}`.
3. Put figure wrappers in `figures/` and image assets in `assets/images/`.
4. Add bibliography entries to `references/references.bib`.
