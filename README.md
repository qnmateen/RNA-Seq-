# RNA-Seq-

## Step involved 

1.Download raw file from sra 
2.Convert to fastq
 *can keep files as zip to save space
3.Perform Fastqc for quality check
4.Perform Multiqc
5.Run Trimmomatic- to remove adaptors, repeated sequences, and short sequences
6.Perform FastQC on trimmed files and  MultiQC to compare with files before trimming.
7.Align the files reference genome using Star or HISAT2
  i) Download gtf file and fasta file from Gencode
  ii) Make index 
  iii) Align the files
  *output bam files will be generated
8.Use featureCount to get raw counts matrix
9.Perform DESeq2 for getting LogFC and p value of differentialy expressed genes.
