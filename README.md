# Functional Sequence Characterization Pipeline

## Overview
This project provides an automated bioinformatics pipeline for characterizing unknown DNA sequences. It performs quality control, identifies Open Reading Frames (ORFs), translates DNA into protein sequences, and executes a functional annotation via NCBI BLASTp to determine the biological role of the sequence.

## Features
- **Sequence Input:** Reads DNA sequences in FASTA format.
- **Quality Control:** Calculates GC content percentage.
- **ORF Discovery:** Scans three reading frames to identify the longest possible protein sequence starting with a Methionine (M).
- **Homology Search:** Submits the translated protein to the NCBI 'nr' database using Biopython's `NCBIWWW` module.
- **Reporting:** Generates a `qc_summary.txt` and a `functional_annotation.txt` report summarizing the biological findings.

## Project Structure
| File Name | Description |
|-----------|-------------|
| `final_code.py` | The main Python execution script. |
| `rat.fasta` | The input DNA sequence (mRNA of Rattus norvegicus Ift20). |
| `protein.fasta` | The output file containing the translated longest ORF. |
| `blast_result.xml` | The raw XML output from the NCBI BLAST server. |
| `qc_summary.txt` | A summary of basic DNA metrics (Length, GC%). |
| `functional_annotation.txt` | The final human-readable report of protein homologs. |

## Requirements
- Python 3.x
- [Biopython](https://biopython.org/) library (`pip install biopython`)
- Active internet connection (for online BLASTp queries)

## Usage
1. Place your DNA sequence in a file named `rat.fasta` in the project directory.
2. Run the script:
   ```bash
   python final_code.py
