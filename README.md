# Librito de estadística

Notas de métodos estadísticos escritas con [bookdown](https://bookdown.org/yihui/bookdown/).
Actualmente el libro contiene el análisis exploratorio (EDA) del precio de la
vivienda en California (`data/housing.csv`).

## Estructura

| Archivo | Contenido |
|---|---|
| `index.Rmd` | Portada y contexto del problema |
| `01-intro.Rmd` | Capítulo de EDA (el único en desarrollo) |
| `06-references.Rmd` | Sección de referencias |
| `_bookdown.yml` | Qué archivos entran al libro y a dónde se compila (`docs/`) |
| `_output.yml` | Configuración de los formatos de salida |
| `data/housing.csv` | Datos |

Para añadir un capítulo nuevo, créalo como `NN-nombre.Rmd` y agrégalo a la lista
`rmd_files` de `_bookdown.yml` (el orden de esa lista es el orden del libro).

## Compilar

Desde RStudio: pestaña **Build** → *Build Book*.

Desde la terminal hay que indicarle a R dónde está pandoc, porque el que viene
con RStudio no está en el `PATH`:

```sh
export RSTUDIO_PANDOC=/Applications/RStudio.app/Contents/Resources/app/quarto/bin/tools/aarch64
Rscript -e 'bookdown::render_book("index.Rmd", "bookdown::gitbook")'
```

(Alternativa: `brew install pandoc` y ya no hace falta la variable.)

El resultado se genera en `docs/`, que es lo que publica GitHub Pages.

## Dependencias

```r
install.packages(c("bookdown", "tidyverse", "Amelia", "moments",
                   "patchwork", "GGally"))
```
