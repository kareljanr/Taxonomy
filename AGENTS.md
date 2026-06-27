# AGENTS.md

## Cursor Cloud specific instructions

This repository is **data/documentation only** — it is the "Taxonomy of public services"
proposal. The only tracked files are `README.md` and an Excel spreadsheet
(`Taxonomy proposal v0.12.xlsx`).

Key facts for future agents:

- There is **no application code, package manifest, build system, test suite, or lint
  configuration** anywhere in the repo or its git history. There is nothing to
  `install`, `build`, `lint`, `test`, or `run`.
- No update/setup script is needed; the environment requires no dependencies.
- The substantive content lives inside the `.xlsx` workbook (12 worksheets). It can be
  inspected without third-party packages because `.xlsx` is a zip archive, e.g.:
  `python3 -c "import zipfile;print(zipfile.ZipFile('Taxonomy proposal v0.12.xlsx').namelist())"`.
  To read cell values conveniently, `pip install openpyxl` (not a repo dependency).
- Contribution workflow is described in `README.md`: edits are made directly in the
  spreadsheet following the ReadMe sheet inside the workbook.
