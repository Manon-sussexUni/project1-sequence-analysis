# Identifying Mutations in NGS Data

## 1. Title and Purpose

This project analyses Next-Generation Sequencing (NGS) reads from *Schizosaccharomyces pombe* (fission yeast) to identify and compare mutation patterns between treated and control samples.

The dataset contains six biological samples: three treatment samples (samples 1–3) and three control samples (samples 4–6), with 1,000 reads per sample. Each read is 200 nucleotides long.

The main objective is to identify mismatches between sequencing reads and a reference sequence, summarise mutation patterns for each sample, and investigate differences between the two experimental groups.

## 2. How to Run

The project is implemented in a Python Jupyter Notebook and can be run using Google Colab.

1. Open the notebook in Google Colab.
2. Make sure `reference.txt` and `reads.csv` are available in the notebook's working environment.
3. Run the notebook cells in order, starting with the imports and data loading sections.
4. Execute the function definitions and their corresponding test cells.
5. Run the final analysis section to analyse all six samples and compare mutation patterns.

## 3. Inputs and Outputs

**Inputs:**
- `reference.txt`: the reference nucleotide sequence.
- `reads.csv`: the sequencing reads from the six biological samples.

**Outputs:**
- Validation results indicating valid and invalid reads.
- Identified mismatches and their positions.
- Sample summaries, including mismatch percentages and substitution patterns.
- The three most frequent mismatch positions across the experimental groups.
- Statistical comparisons between control and treatment samples using a two-sided Welch's t-test.

## 4. Code Design

The analysis is organised into five main functions:

- `validate_read()`: checks whether a sequencing read is valid.
- `find_mutations()`: identifies mismatches between a read and the reference sequence.
- `analyse_reads()`: analyses the sequencing reads.
- `summarise_samples()`: summarises mutation patterns for each biological sample.
- `compare_positions()`: identifies the most frequent mismatch positions and compares the two groups statistically.

The functions are designed to work together, with each step using the results produced by the previous one.

## 5. Testing

Each function was tested using the provided dataset and additional custom test cases. These tests cover normal inputs, empty datasets, invalid reads, and other relevant edge cases.

The final analysis showed a higher overall mismatch rate in the treatment group (60.33%) than in the control group (8.33%). Positions 97, 98 and 99 showed statistically significant differences between the groups (p < 0.05).

The interpretation also considers the distinction between overall mismatch rates and position-specific mismatch percentages, since these measurements describe different aspects of the mutation patterns.
