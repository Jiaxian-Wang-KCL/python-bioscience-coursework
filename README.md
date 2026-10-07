# Python for Bioscience — Jiaxian Wang

Coursework and practice archive for **5BBB0238 — Introduction to Programming for Bioscientists**, with a selected promoter-sequence analysis portfolio.

This repository now includes all **87 supplied source files (50 Jupyter notebooks)**, alongside the existing documented sequence-analysis project. The collection covers Python basics, DNA sequence processing, mathematical modelling, functions, dictionaries, debugging and image processing.

## Browse the work

| Area | Examples | Where to look |
| --- | --- | --- |
| Assessed and formative coursework | Summative 2024–5 and 2025–6, formative coursework, formative exam | [Complete notebook index](COURSEWORK_INDEX.md) |
| Fundamentals | Variables, loops, slicing, lists and dictionaries | `coursework/CodingClub_W1.ipynb`, week 2–3 notebooks |
| Sequence analysis | Promoter motifs, restriction enzymes, CRISPR guide sequences | Summative notebooks, revision questions and week 3/7 notebooks |
| Mathematical modelling | Bacterial growth, potato example, pre-culture calculations | Week 4 notebooks and modelling examples |
| Functions and debugging | Reusable functions, maze, filter selector and song exercises | Function practice and debugging notebooks |
| Image processing | Thresholding, image arrays and Pearson correlation exercises | Week 8 notebooks and `coursework/image_processing_data/` |

The [coursework index](COURSEWORK_INDEX.md) links to every notebook and reports empty cells and saved errors. [The manifest](coursework_manifest.json) lists every original source file and its checksum.

## Selected analysis: promoter sequences

The existing [promoter notebook](notebooks/promoter_sequence_analysis.ipynb) and [analysis report](PROMOTER_ANALYSIS.md) explain the problem, input DNA, methods and previously checked results. These include a first `TATAA` match at index 432 and candidate TSSs at 854, 2259, 3240 and 3243 under the exercise's spacing rule. Positions use zero-based indexing. These are sequence-search results, not experimental evidence of biological function.

The selected portfolio covers exercises 1–7 of the 2025–6 notebook. The complete original assessment notebooks, including their final exercises and existing code or empty cells, are now preserved in `coursework/`.

## Open the notebooks

Use Python 3 and JupyterLab. Install the packages in `requirements.txt`, then start JupyterLab from `coursework/` for original top-level notebooks, or from the repository folder for the selected portfolio notebook. The original materials use the standard library, NumPy and Matplotlib. Some cells request interactive input, rely on previous cells, or write files.

```sh
python3 -m pip install -r requirements.txt
cd coursework
python3 -m jupyterlab
```

## Provenance and status

This is a private archive supplied by **Jiaxian Wang**. It includes student work together with teaching templates, sample code, explicitly named reference solutions and deliberately buggy exercises. The collection is not represented as entirely original student-authored code or as entirely completed work. Both assessment-year versions and duplicate variants are retained with their original filenames.

Course questions, supplied datasets, images and reference solutions retain their original provenance; no ownership or redistribution licence is asserted over those materials.

The new archive was checked for file completeness, byte-for-byte fidelity, notebook JSON validity and Python syntax. Original notebooks were not run or edited during this update. The existing selected analysis and its previously saved verification record remain available; its verification scope is documented in [editing notes](EDITING_NOTES.md). AI assistance was used for repository organisation, documentation and archive checks.
