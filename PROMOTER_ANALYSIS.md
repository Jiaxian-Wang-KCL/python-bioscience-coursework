# Python for Bioscience: Promoter Sequence Analysis

A portfolio edition of my completed sequence-analysis work for **5BBB0238 — Introduction to Programming for Bioscientists, Summative Coursework 2025–6**.

I used Python to read DNA sequences, search for short motifs and identify candidate transcription start sites under the rules supplied in the coursework. The project demonstrates string slicing, loops, conditionals, lists, dictionaries, file handling and a reusable function.

## What problem does this address?

Given a DNA sequence, where are the specified promoter motifs, and which combinations satisfy the exercise's spacing rule for a potential transcription start site (TSS)? A second analysis locates exact matches to five simplified transcription-factor binding-site motifs.

## Data

| File | Length | Use |
| --- | ---: | --- |
| `data/seq1.txt` | 500 bases | First TATA-box match, initiator-like pairs and binding-site motif searches |
| `data/seq2.txt` | 4,000 bases | Candidate TSS search and surrounding sequence display |

Both are plain-text DNA sequences provided with the coursework. The coursework describes `seq1.txt` as a human gene promoter region, but the files do not provide a gene identifier, genome assembly or accession. Positions below refer to these input strings, not genomic coordinates. The exercise and data originate from course materials; no redistribution licence is asserted here.

## Methods

1. Read the sequence files and remove surrounding whitespace.
2. Search for the exact TATA-box string `TATAA`.
3. Identify initiator-like `YR` pairs, where `Y` is C or T and `R` is A or G.
4. Report a candidate TSS when the second base of a `YR` pair is 24–31 bases downstream of the first base of a `TATAA` match.
5. Display 50 bases before each candidate TSS and 50 bases starting at it.
6. Scan `seq1.txt` for the course's five simplified binding-site strings, retaining overlapping matches.

All positions use **zero-based indexing**. Searches are on the supplied forward sequence only.

## Results

The completed analysis produced these independently checked results:

| Analysis | Result |
| --- | --- |
| First `TATAA` in `seq1.txt` | Index **432** |
| `YR` pairs within the first 30 bases of `seq1.txt` | **5** matches, starting at **0, 6, 8, 14, 23** |
| Candidate TSSs in `seq2.txt` | **854, 2259, 3240, 3243** |
| Sequence context | Four 100-base windows, each split immediately before its candidate TSS |

| Motif label | Exact string | Match positions in `seq1.txt` |
| --- | --- | --- |
| PDX1 | `TCTAAT` | 143, 246 |
| NKX6-1 | `TAATTAA` | 392 |
| MAFA | `TGCA` | 122, 334, 479 |
| SP1 | `CCGCCC` | 116 |
| NFY | `CCAAT` | No exact match |

These are outputs of a simple sequence-search exercise. They do **not** establish functional promoters, actual protein binding or gene-expression effects. There is no experimental validation or statistical enrichment test in this project.

## Run the notebook

Use Python 3 and Jupyter. From the repository folder:

```sh
python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install -r requirements.txt
python3 -m jupyterlab
```

Open [`notebooks/promoter_sequence_analysis.ipynb`](notebooks/promoter_sequence_analysis.ipynb) and run the cells from top to bottom. The analysis itself uses only the Python standard library.

```text
python-bioscience-coursework/
├── README.md
├── EDITING_NOTES.md
├── requirements.txt
├── data/
│   ├── seq1.txt
│   └── seq2.txt
├── notebooks/
│   └── promoter_sequence_analysis.ipynb
└── results/
    └── verified_results.json
```

## Scope and editing

This edition covers the completed analysis in exercises 1–7. The source notebook's final random sequence-generation exercise was unfinished and is excluded; it is not claimed as completed work.

The original coursework file is unchanged. Portfolio preparation used AI assistance for documentation, file paths, checking outputs and correcting the sequence-context display. The student's motif-search logic is retained. See [editing notes](EDITING_NOTES.md) for the exact changes.

**Verification:** all eight code cells, including setup, were executed sequentially using Python 3.12. The reported results were checked independently, including the corrected context display and a sequence-boundary case. A fresh Jupyter kernel could not be launched in the restricted verification environment, so end-to-end Jupyter execution is not claimed. Refreshed outputs are saved in the notebook and the checked results in [`results/verified_results.json`](results/verified_results.json).
