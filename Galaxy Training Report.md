# GALAXY TRAINING REPORT

---

 **INTRODUCTION**
 
Having attended a [Galaxy](https://usegalaxy.eu/) training program from 15th February 2021 to 19th February 2021, the following is an account of all the different analysis workflows that I was exposed to as well as the skills that are gained during the training period.
Galaxy is a web-based and user-friendly data analysis platform that allows one to use a variety of tools to analyse a wide range of biological data over a significantly short period of time hence reducing the data analysis burden on the modern-day bioinformatician. The tools are developed using various scripting languages such as Python and R and are set in an interactive format that allows for parameter modification based on the need of the specific analysis at hand. The fact that Galaxy is able to handle raw data, analyze it and give desired results in one environment makes it a suitable platform to carry out bioinformatics workflows. Nucleotide sequence data from both long-read sequencing(eg.Nanopore) and short-read sequencing (eg.Illumina) are the most common form of input for analysis, with the data encoded in fastq format. Peptide sequence data from Liquid Chromatography/Mass Spectrometry protocols can also be used for proteomic and/or proteogenomic analysis(mostly encoded in MGF. format)
With the ability to support various workflows, Galaxy can be used to create different analysis pipelines of genomic importance.These include sequence quality control, genome mapping/alignment, genome annotation, genome assembly,variant calling among others that will be described later in this document.
Moreover, it is reproducible in nature .
The Galaxy suite is also convenient in that it can be personalized to a particular institution to cater for specific needs. This serves to mean that one can create a Galaxy instance that contains specific tools required for building workflows that are tailored to an institutions needs.
The main servers, however, are based in Europe(usegalaxy.eu) , Australia (usegalaxy.au) and USA (usegalaxy.com)

The tutorials were followed in a sequential order as listed below;

1. Introduction to Galaxy Worflows
- Quality Control
- Genome Mapping
- Genome Assembly

2. Introduction to RNA-Seq analysis with Galaxy and R  
  
- Reference based RNA-Seq
- Starting R in Galaxy 
- RNA postprocessing with R

3. Single Cell RNA-Seq Analysis
  - Pre-processing of 10x Single-Cell RNA datasets
  - Clustering singel-cell RNA-Seq data using ScanPy

4. Proteomics
- Creating a proteogenomics database
- Searching a proteogenomics database
- Novel peptide analysis
- Metagenomics

---
 ## Introduction to Galaxy Workflows
   *Quality control* is a major protocol that is undertaken when handlinng sequence data that has been produced after sequencing. It serves to check, as the name suggests, the quality
   of the sequences so that they can be validated for other downstream processes such as genome mapping or variant calling. Galaxy has tools that enable the user to perform routine
   quality checks which include FastQC and MUltiQC. FastQC provides a set of analysis paremeters that allow one to note any error in their reads while MultiQC gives a colective report on
   different FastQC raw files hence giving a summary quality report of several reads at once. The quality report generated contains different facets of analysis such as 
   - Per base sequence quality
   - Per sequence quality scores
   - Per GC content
   - Sequence Duplication Levels
   - Overrepresented sequences
   
   The Phred Score(sometimes referred to as the QScore) is the major score used to determine base call accuracy of the reads.The best score is a Quality Score of Q30 which means that
   the base call accuracy was 99.9%. Mathematically, this is defined by a 1 in 1000 probability. However, different scores maybe accepted depending on various factors such as the type of raw sequence
   data being analyzed.
   
   **Genome Mapping** refers to aligning of the reads to a reference genome so as to visualize their locations in the genome which may later aid in annotation processes.The reference genome used varies with
   the origin of the reads and Galaxy provides a parameter that contains built-in reference genomes for the most common species, both plants and animals. Galaxy also provides a host of tools
   for mapping protocols the most common being bowtie2, BWA-MEM, RNA-STAR(for RNA-Seq) and HISAT.Any tool can be used depending on the user's output of interest. The output is mostly in a
   BAM(Binary Alignment Map) file formart which is a compressed binary file storing the read sequences ans showing the position on the reference sequence at which they have been aligned.
   Visualization can then be carried out using a web-based Galaxy tool known as JBrowse or a visualization tool known as IGV(Integrative Genome Viewer)
   
   **Genome Assembly** involves joining together DNA sequence reads in de novo fashion using various tools which could even result in the assembly of an entire chromosome. An assembled genome could
   later be used a reference platform for different types of analysis. Quality checks are first carried out on the reads after which assembly is carried out using different Galaxy-based tool such as
   Flye or Unicycler. The assembled data can then be visualized using Bandage, a built-in Graphical viewer in Galaxy. The assembly can be polished further by mapping short reads to the assembly(BWA-MEM) and using 
   Pilon/Racon to compare short reads to the assembly and hence create a polished version.Annotation is then carried out using Prokka and can be visualized using Jbrowse.
 ---  
   
   **RNA Seq Analysis with Galaxy and R**
   
   **RNA-Seq Analysis** involves analysis of the whole transcriptome in a high throughput manner.This analysis is usually met by various shortcomings suchas incompletely processed RNAs or transcriptional background
   noise,sequencing biases and the presence of introns in the reference genome used.Reference-based RNA-Seq analysis is commonly used and Galaxy provides different tools that circumvent the
   challenges that have been highlighted. Using a Galaxy Workflow, the raw sequence reads undergo quality control using FASTQC after which any adapters present are trimmed using
   Cutadapt. The trimmed reads are then mapped using RNA-STAR where MultiQC can be used to check the mapping quality. THe mapping files can then be visualized using different genome browsers.The strandness of the reads is 
   then estimated using the Infer Experiment tool after which the number of reads per gene is deduced with the aid of the featureCounts tool. This is essential especially for further expression analysis.
   Diffrerentially expressed features can then be identified and in this case, a gene is declared differentially expressed if a change is observed in read counts or expression levels
   between two experimental conditions.Differential expression analysis is done using the DESeq2 tool which estimates the biological variance as well as the significance of expression differences.
   The analysis generates statistical plots such as PCA plots, dispersion estimates and a histogram of p-values that can be used to ascertain expression levels.
   Differentially expressed genes are extracted and annotated and visualized using heatmaps.Finally, functional enrichment analysis is carried out which involves gene ontology analysis and KEGG pathway analysis using the 
   goseq tool.
   *R* was then introduced as an important tool for biologists especially for handling tabular data and visualizing RNA-Seq post-processed data. This was done using different R libraries such as
   tidyr and dplyr afterwhich visualization was done using the ggplot2 tool.
   ---
   
   **Single Cell RNA-Seq Analysis**
   
   **Single Cell RNA-Seq analysis** (abbreviated as scRNA-Seq analysis) involves the analysis of individual cells within tissues and gives more information about the individual gene expression per cell
   In this case, differential expression analysis may involve some cells expressing the same set of genes in the same way and hence one set of cells can be compared against another
   This is different from Bulk RNA-Seq analysis which involves analysis of the average gene expression per tissue.Barcodes are mostly used to mark reads in scRNA-seq.A quality check is first performed on the reads after which
   the barcodes(Unique Molecular Identifiers - UMIs) are then united with the sequences using the UMI tools extract tool.The cell and UMIs are then transferred to the reverse reads which are used
   for downstream processes.Preprocessing of 10X Single -Cell RNA datasets was also performed using reads that have been generated using the 10X sequencing technology This involved generating a count matrix from FASTQ by
   demultiplexing which uses barcode information to know which sequences came from which sample. This is done using the RNA-Star Solo mapping tool that results in different output files such as a log file, alignments, matrix,
   barcodes and genes. A quality count matrix is then produced to give the number of cells that have been differentially expressed ; this is accomplished by the DropletUtils tool.
   To practise on scRNA-Seq analysis, clustering scRNA-Seq data using ScanPy was carried out so as to undertand how cell differentially expression can be analyzed using clusters represented in statistical 
   output.
   ---
   
   **Proteomics**
   Proteomics refers to the large scale study of proteins in an organism, that is, proteins whhcih are either produced or modified  by the organism. We concentrated on a specific field of proteomics called
   proteogenomics which used mass spectrometry based proteomics data against genomics and transcriptomics data to identify peptides and understand protein level evidence of gene expression.
   This is divided into three facets: creating a proteogenomics database, searching a proteogenomics database and novel peptide analysis.
   When creating a proteogenomics databse, the FASTQ files are first mapped to a reference genome using the HISAT2 tool after which variant analysis and variant annotation are done using FreeBayes and CustomProDB respectively.
   The transcripts are assembled using StringTie and the assembly is evaluated with annotated transcripts using GffCompare. The transcripts are then translated to proteins are FASTA Databases are created using the FASTA MERGE FILES tool.
   The proteogenomics database is then searched using mass spectrometry files (MGF files) as the input files. The database is searched using the SearchGUI tool so as to match the peptide sequences. Peptide shaker is then used to assess
   the confidence of data by generating a PSM report and certificate of analysis. A SQLite database is then created for peptide, protein and genome annotation visualization. The known proteins are
   removed from the list of PSM and the data is at that moment ready for novel peptide analysis.
   Novel peptide analysis is achieved using BlastP feature present in the NCBI Query Platform. However, Galaxy conveniently provides a tool known s NCBI BLAST + blastp  which gives the desired possible protein hits. One can also 
   utilize the Multiomics Visualization Program provided by Galaxy to view selcted peptides for further analysis. The peptide genomic coordinates are then obtained using the Obtaibing Coordinates tool afterwhich the peptides are classified
   using the PepPointer tool.
   Moreover, a metaproteomics workflow was ran where metaproteomics is the large-scale characterization of the entire collection of proteins in the environmental microbiota. In the Galaxy workflow, the input files are the MGF files which are searched 
   against a metapeptides database using the SearchGUI tool afterwhich Peptide Shaker gives an assesment of the data through a PSM report. Different analyses are then undertaken such as taxonomy analysis and a functional analysis.
   ---
 
   **Galaxy Analysis Workflows**
   Using the skills obtained after the training, I was able to carry out different analyses using datasets that are provided by the Galaxy Training Network.
   You can find below the link to my histories if you would like to follow through my analysis pipeline.
   
   - *Annotating a prokaryotic genome* - [Genome Annotation](https://usegalaxy.eu/u/hebrewsimeon/h/annotating-prokaryotic-genome)
   - *M.tuberculosis variant analysis* - [Variant Analysis](https://usegalaxy.eu/u/hebrewsimeon/h/mtuberculosis-variant-analysis)
   - *ProteoRE tool for biomarker discovery* - [Protein Annotation](http://www.proteore.org/u/hebrewsimeon/h/protein-annotation)
   
 

