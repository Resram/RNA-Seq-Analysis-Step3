## Step 6: Read Alignment with HISAT2

Normally, in RNA-Seq workflows, the first step for alignment involves building an index of the reference genome using HISAT2. This index is crucial for efficient alignment of RNA-seq reads to the genome. However, since you already have the HISAT2 index files located in the chrX_data/indexes folder (specifically chrX_tran), this step is skipped.

If you ever need to build the index from scratch (for a different genome or project), you would use the following command:

```bash
hisat2-build Homo_sapiens.GRCh38.dna.primary_assembly.fa hisat_index
```
---
Homo_sapiens.GRCh38.dna.primary_assembly.fa: The reference genome file (e.g., GRCh38 human genome).
Since the index is already available, you can skip this step and move directly to the alignment step.

## Step 7: HISAT2 Alignment
Once the reference genome index is available (as in your case), the next step is aligning the RNA-seq reads to the reference genome using HISAT2. Below is an explanation of how to use HISAT2 to perform the alignment.
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188044_chrX_1.fastq.gz -2 chrX_data/samples/ERR188044_chrX_2.fastq.gz -S ERR188044_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188104_chrX_1.fastq.gz -2 chrX_data/samples/ERR188104_chrX_2.fastq.gz -S ERR188104_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188234_chrX_1.fastq.gz -2 chrX_data/samples/ERR188234_chrX_2.fastq.gz -S ERR188234_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188245_chrX_1.fastq.gz -2 chrX_data/samples/ERR188245_chrX_2.fastq.gz -S ERR188245_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188257_chrX_1.fastq.gz -2 chrX_data/samples/ERR188257_chrX_2.fastq.gz -S ERR188257_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188273_chrX_1.fastq.gz -2 chrX_data/samples/ERR188273_chrX_2.fastq.gz -S ERR188273_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188337_chrX_1.fastq.gz -2 chrX_data/samples/ERR188337_chrX_2.fastq.gz -S ERR188337_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188383_chrX_1.fastq.gz -2 chrX_data/samples/ERR188383_chrX_2.fastq.gz -S ERR188383_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188401_chrX_1.fastq.gz -2 chrX_data/samples/ERR188401_chrX_2.fastq.gz -S ERR188401_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188428_chrX_1.fastq.gz -2 chrX_data/samples/ERR188428_chrX_2.fastq.gz -S ERR188428_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR188454_chrX_1.fastq.gz -2 chrX_data/samples/ERR188454_chrX_2.fastq.gz -S ERR188454_chrX.sam
```
```bash
hisat2 -p 8 --dta -x chrX_data/indexes/chrX_tran -1 chrX_data/samples/ERR204916_chrX_1.fastq.gz -2 chrX_data/samples/ERR204916_chrX_2.fastq.gz -S ERR204916_chrX.sam
```
---
## Step 8: SAM to BAM Conversion

Overview

The samtools sort command is an essential step in processing RNA-Seq data after alignment. This step organizes the alignments in the SAM file and saves the result as a compressed BAM file (binary format), which is more efficient for downstream analysis.
### Install the required tools into your conda environment

```bash
samtools sort -@ 8 -o ERR188044_chrX.bam ERR188044_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR188104_chrX.bam ERR188104_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR188234_chrX.bam ERR188234_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR188245_chrX.bam ERR188245_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR188257_chrX.bam ERR188257_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR188273_chrX.bam ERR188273_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR188337_chrX.bam ERR188337_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR188383_chrX.bam ERR188383_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR188401_chrX.bam ERR188401_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR188428_chrX.bam ERR188428_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR188454_chrX.bam ERR188454_chrX.sam
```
```bash
samtools sort -@ 8 -o ERR204916_chrX.bam ERR204916_chrX.sam
```
