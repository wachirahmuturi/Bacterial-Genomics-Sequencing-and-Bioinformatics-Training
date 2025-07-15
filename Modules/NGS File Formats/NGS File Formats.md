# Computational Practical 3
# NGS File Formats
## Module Developer: Collins Kigen
## 1.0 Introduction
<img width="768" height="464" alt="image" src="https://github.com/user-attachments/assets/da1c7731-228f-48e4-b81c-342a98a548d8" />



### Fastq file
FASTQ files are text files containing sequence data with a quality (Phred) score for each base, represented as an ASCII character. 
<img width="553" height="311" alt="image" src="https://github.com/user-attachments/assets/8ebc939d-6a86-4266-82cd-7435086d955f" />
## Phred Quality Scores Explained

Phred quality scores (`Q`) are logarithmically related to base-calling error probabilities (`P`) and are defined as:

Q = -10 * log10(P)


This relation can also be expressed as:

P = 10^(-Q/10)


For example:
- If `Q = 30`, the probability that this base is called incorrectly is **1 in 1,000**.

---

### ✅ Quick Reference Table

| **Phred Quality Score (Q)** | **Probability of Incorrect Base Call (P)** | **Base Call Accuracy** |
|------------------------------|--------------------------------------------|--------------------------|
| 10                           | 1 in 10                                    | 90%                     |
| 20                           | 1 in 100                                   | 99%                     |
| 30                           | 1 in 1,000                                 | 99.9%                   |
| 40                           | 1 in 10,000                                | 99.99%                  |
| 50                           | 1 in 100,000                               | 99.999%                 |
| 60                           | 1 in 1,000,000                             | 99.9999%                |

---

## 📄 FASTA Files

The **FASTA** format is widely used for representing nucleotide or protein sequences. Each entry in a FASTA file consists of:

- A **header line** starting with `>` followed by a sequence identifier and optional description.
- One or more lines of the **sequence** (DNA, RNA, or protein).

### ✅ Example FASTA Entry (DNA)
<pre>
>sequence_1 description
ATGCGTATCGACTAGCTAGCTAGCGTAGCTAGCTA
ATGCTAGCTAGCTAGCTAGCTAGCGATCGATGCT
</pre>

<pre>
>protein_1 description
MTEYKLVVVGAGGVGKSALTIQLIQNHFVDEYDPT
IEKQYKSTIGAAK
</pre>
---

### 🔍 Notes:
- Sequences should **only contain valid IUPAC characters** (A, T, G, C for DNA).
- No blank lines are allowed between header and sequence.
- FASTA files are commonly used as input for tools like BLAST, genome assembly, and alignment software.

---

### 📂 Typical Use Cases
- **Reference genomes** for mapping.
- **Protein databases** for homology searches.
- **Input for bioinformatics pipelines**.

---

## 📚 Additional Resources
- [FASTA format specification](https://blast.ncbi.nlm.nih.gov/doc/fasta.html)
- [NCBI FASTA download](https://www.ncbi.nlm.nih.gov/)




## Exercise
1. Open the first 10 lines of seq.fastq
2. Write a code to count the number of reads in seq.fastq
3. open the first 5 lines of seq.fasta
4. List all the header lines of seq.fasta
5. Count the number of sequences in seq.fasta
