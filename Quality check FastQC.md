# FastQC

The *fastq format* is also a *text based format* to represent nucleotide sequences,    
but ***also contains the corresponding quality*** of each nucleotide.    
It is the standard for storing the output of high-throughput sequencing instruments such as the Illumina machines.   

### A fastq file uses four lines per sequence:   

**Line 1** begins with a '@' character and is followed by a sequence identifier and an optional description (like a FASTA title line).   
**Line 2** is the raw sequence letters.   
**Line 3** begins with a '+' character and is optionally followed by the same sequence identifier (and any description) again.   
**Line 4** encodes the quality values for the sequence in Line 2, and must contain the same number of symbols as letters in the sequence.  

**@SEQ_ID
GATTTGGGGTTCAAAGCAGTATCGATCAAATAGTAAATCCATTTGTTCAACTCACAGTTT
+
!''*((((***+))%%%++)(%%%%).1***-+*''))**55CCF>>>>>>CCCCCCC65
**

### Quality¶

The quality, also called ***phred score***, is the probability that the corresponding basecall is incorrect.

Phred scores use a logarithmic scale, and are represented by ASCII characters, mapping to a quality usually going from 0 to 40.

# Command

fastqc -t 8 -o fastqc/ SRR*  
-t thread 8   
-o output fastqc folder    
file name SRR*   
