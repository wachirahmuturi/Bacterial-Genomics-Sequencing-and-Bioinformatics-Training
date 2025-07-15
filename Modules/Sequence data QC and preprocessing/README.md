# Computational Practical 3
# Sequence Data Quality Control
## Module Developer : Collins Kigen
## Introduction
A typical whole genome sequencing process involves genomic DNA isolation, library preparation and sequencing. Errors can be introduced during the library preparation and sequencing steps which may cause inaccurate representations of the original DNA sequences. 

Potential problems or quality related issues with raw next generation sequencing (NGS) data include:

1. Low base quality \- sequencing technologies can produce reads with varying quality
2. Contamination with adapter sequences
3. Base composition biases  
4. GC content distribution
5. Sequence duplication 

***Several tools are available for performing quality control and preprocessing of fastq data*** 

Some popular standalone tools tools include:

1. FASTQC \- quality control tool for visualizing key quality profiling metrics  
2. Cutadapt \- adapter removal and read filtering  
3. Trimmomatic \- adapter removal, read pruning and filtering e.g. using sliding window cutting  
4. TrimGalore \- a wrapper tool around cutadapt and FASTQC

In recent years tools that integrate both quality control and read filtering have been developed, such as TrimGalore, AfterQC, fastp, etc. In this practical we will introduce and use fastp for raw data quality control, filtering, adapter removal and base correction for fastq data. Fastp is an ultra-fast multithreaded tool that incorporates most features of fastqc, cutadapt, trimmomatic and AfterQC, and is best suited for short reads, but with basic support for long read data QC.

> For visualization of quality metrics we will use MultiQC

The preprocessing of FASTQ data, which means removing adapter contamination, filtering low-quality reads, and correcting wrongly represented bases, is an indispensable but resource intensive part of sequencing data analysis.

**2.1 Fastq format**   
In NGS, fastq data format is broadly adopted as the standard for the raw output data regardless of the sequencing platform and the sequencing throughput. 


**2.2. (Phred) Quality Scores Interpretation**


FASTQ data need to go through quality control and a series of preprocessing steps before they can enter the downstream analysis to ensure that clean and accurate reads are processed downstream.

## 2.3 Common QC metrics for raw data

## Removal of adapter contamination

* Sequence-matching based adapter trimming  
- Tools: Cutadapt, Trimmomatic etc.  
* Adapter trimming based on finding overlaps of read-pairs  
- Tools: Fastp, AfterQC  
- Automatic adapter detection

### Base correction

* Mainly applied to paired-end data  
* Only base pairs with an imbalance quality score are corrected

### Improving read quality

* Sliding window quality pruning method  
  * Drops low quality bases in each reads 5\` or 3\` region  
* Filtering reads using a low-quality base percentage, N base number and read length

### Trimming of polyG and polyX tails

Some Illumina sequencing platforms such as the NextSeq series can produce reads with polyG tails due to their fluorescence chemistry resulting in some T and C bases being interpreted as Gs in read tails when signal strength of each cluster becomes weaker in subsequent cycles. The polyG tail issue can result in a serious base content separation problem, meaning that A and T or C and G have substantially different base content ratios. 

### Overrepresented sequence analysis

Some sequences, or even entire reads, can be overrepresented in FASTQ data. Analysis of these overrepresented sequences provides an overview of certain sequencing artifacts such as PCR over-duplication, polyG tails and adapter contamination.

### Hands-on exercise 1: (20 min)
