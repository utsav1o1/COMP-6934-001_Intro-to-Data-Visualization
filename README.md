# COMP-6934-001_Intro-to-Data-Visualization

## Course Project: Less Fish, More Money — Canada's Commercial Sea Fisheries, 1990–2024

COMP 6934 (Data Visualization), Memorial University — Group 16: Utsav Karki, Lata Airee, Abishek Paudel.

### Layout

```
data/     DFO landings CSV (source data) + Statistics Canada CPI (for inflation adjustment)
code/     fisheries_analysis.ipynb — cleans the data and produces every figure in the report
figures/  fig1–fig7 as vector PDF (used by LaTeX) and PNG previews
report/   report.tex (LaTeX source, 12 pt) and the compiled report.pdf
proposal/ proposal.tex and the compiled 1-page proposal.pdf
```

### Reproduce the figures

```bash
pip install -r requirements.txt
cd code
jupyter nbconvert --to notebook --execute --inplace fisheries_analysis.ipynb
```

Or open `code/fisheries_analysis.ipynb` in Jupyter / VS Code and run **Restart & Run All**.
All seven figures are rewritten to `figures/`.

### Build the report

```bash
cd report
pdflatex report.tex && pdflatex report.tex     # or: latexmk -pdf report.tex, or upload to Overleaf
```

On Overleaf, upload `report/report.tex` and the `figures/` folder, keeping `figures/` one
level above the .tex file or changing `\graphicspath` to `{figures/}`.

### Data sources

* Fisheries and Oceans Canada (2025). *Commercial Seafisheries Landings, 1990–2024*, Zonal Interchange File database.
* Statistics Canada, Table 18-10-0005-01, Consumer Price Index, annual average (2002 = 100).
