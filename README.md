# introCausal

A very personal and courageous introduction to causal inference

This repository contains the materials for a 40-minute Melbourne Integrative
Genomics journal-club session, with 20 minutes for discussion. The deck uses
three papers to ask what causal inference can—and cannot—deliver in
observational and experimental biology.

## Read the slides online

<https://jiadongm.github.io/introCausal/>

## Materials

- `slides.Rmd`: xaringan source deck.
- `slides.css`: presentation styling.
- `slides.html`: rendered deck for browser presentation.
- `PLAN.md`: the session thesis, narrative and timing plan.

The source papers remain in `refs/` locally but are ignored by Git, so they are
not published with the repository.

## Render

```sh
RSTUDIO_PANDOC=/Applications/RStudio.app/Contents/Resources/app/quarto/bin/tools/aarch64 \
Rscript -e 'rmarkdown::render("slides.Rmd", output_file = "slides.html")'
```
