Enoch Ghosh
#Introduction
My work for the assignment 4 involves a de novo genome assembly of Escherichia coli B REL606 using publicly available data. The dataset was obtained from the NCBI Sequence Read Archive under accession SRR2584863 and was part of a long-term evolution experiment. Sequencing was performed on an Illumina HiSeq 2500 platform, producing paired-end short reads. Short-read assembly tools were selected due to the high accuracy and depth of Illumina data. FastQC and fastp were used for quality assessment and filtering, SPAdes for assembly, and QUAST and BUSCO for quality evaluation.
#Methods
A short-read de novo assembly approach was employed using paired-end Illumina sequencing data. Quality of the raw reads was assessed using FastQC. Reads were then processed using fastp, this helped in adapter trimming, quality filtering, and removal of low-quality reads. Genome assembly was then performed using SPAdes. Default parameters were used with multi-threading enabled to improve computational efficiency. SPAdes construct a de Bruijn graph to assemble reads into contigs, making it particularly suitable for bacterial genomes with relatively low complexity and high coverage.
Assembly quality was evaluated using QUAST, which calculates metrics such as N50, L50, GC content, and total assembly length. BUSCO (v5.4.7) was used to assess completeness based on the bacteria_odb10 lineage dataset.
#Results
The final assembly produced a total of 74 contigs ≥500 bp, with a total assembly length of 4,553,510 bp. The largest contig was 348,113 bp, and the N50 value was 153,581 bp, indicating moderate assembly contiguity. The GC content was 50.73. No ambiguous bases were present, suggesting a high-quality assembly without unresolved regions.
BUSCO analysis revealed 100% completeness, with all 124 expected single-copy orthologs identified as complete and single-copy (S:100%), and no duplicated, fragmented, or missing BUSCOs. 
#Discussion
Overall, the assembly quality is high, as indicated by the strong BUSCO completeness score and consistency with expected genome size and GC content. The N50 value and contig count suggests contiguous assembly for a short-read data, although fragmentation remains due to the limitations of short-read sequencing.
Potential improvements could be by incorporating long-read sequencing data (like Oxford nanopore or PacBio) to generate a hybrid assembly and improve contiguity. One major challenge I encountered during this workflow was resolving conda dependencies , particularly for BUSCO.
#References
1.NCBI SRA Data: https://trace.ncbi.nlm.nih.gov/Traces/?run=SRR2584863 ; https://www.ncbi.nlm.nih.gov/bioproject/PRJNA295606 
2.SPAdes: https://ablab.github.io/spades/ 
3.BUSCO: https://docs.hpc.qmul.ac.uk/apps/bio/busco/ 
4.QUAST: https://quast.sourceforge.net/ 
