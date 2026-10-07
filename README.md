# Code and results for "Finite-Sample Guarantees for Robust Whitening"

Repository: https://github.com/abdelhamidzaidi/robust-whitening-margin

Archived version (v1.0): [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23024127.svg)](https://doi.org/10.5281/zenodo.23024127)

Appendix G of the manuscript lists every function of this repository, its purpose and its link to the paper.

## Contents
- `*.py`           the code (Appendix G, Table 9 lists what each file does)
- `run_all.py`     reruns every simulation (any system; `run_all.sh` does the same on macOS/Linux) and regenerates every table and figure (about 1.5 h on one core)
- `results.zip`    the stored result files (.pkl) used for the manuscript, and `tables_output.txt`,
                   the printed output of make_tables.py. Unzip it to obtain the folder `results/`
                   (on Windows: right-click > Extract All, then keep the folder name `results`).
- `requirements.txt` exact library versions (Python 3.12.3)

## First, a five-minute installation test
       pip install -r requirements.txt
       python run_all.py --smoke      # tiny sample sizes; checks that everything runs

## Two ways to use the archive
1. Regenerate the tables and figures from the stored results (a few minutes):
       pip install -r requirements.txt
       (unzip results.zip first)
       cd results
       python ../make_tables.py > tables_check.txt     # compare with tables_output.txt
       python ../make_figures.py                         # writes fig_*.pdf
2. Rerun the simulations from scratch (about 1.5 h):
       python run_all.py        # Windows, macOS or Linux
       sh run_all.sh            # alternative on macOS or Linux

All random numbers come from fixed seeds (Appendix F), so option 2 reproduces the stored
results exactly on the same software versions; computing times vary between computers.

Verification: from a clean copy, a complete rerun reproduced all 141 stored result files
value by value (apart from computing times) and every line of results/tables_output.txt.
