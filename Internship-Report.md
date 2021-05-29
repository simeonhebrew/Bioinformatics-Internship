# Bioinformatics Internship Report  :chart_with_upwards_trend:

## Introduction 

The following is an account of my four month bioinformatics internship with respect to the goals that I had set out to achieve by the
end of the incubation program. The descriptions given define what I have been exposed to so far, steps I have made towards attaining desired competence and the
challenges I have encountered during the same. Conclusively, I have provided highlights of the mini-project that I was tasked with at the end of the internship. 
The aims that I had set with regards to the program were divided into specific sub-themes which were;

1) Learning Collaborative Tools - Slack and GitHub
2) Understanding Genomic Data Management and Reproducibility in bioinformatics
3) Comprehending computational methods for biological data analysis - Programming using Bash scripting, Python and R.
4) Understanding principles and key concepts in bioinformatics.
5) Participating in a mini-project

## Learning Collaborative Tools :wrench:
I was introduced to tools that enhance efficient team collaboration while undertaking computational tasks. These tools were Slack and GitHub. Slack is a platform
that allows for easy and reliable team communication either at a group level(using channels that are specified to a unique tasks) or at an individual-to-individual
basis (direct messaging feature). I have become efficient in utilizing it as my primary medium of communication whenever there is information to relay other
team members. I have also explored other features that the platform offers such as adding hyperlinks using the Block-Kit Builder. 
I was also introduced to GitHub as a version control platform for collaborative assignments. The key elements of GitHub that I was able to appreciate and apply over
time include;
* Creating repositories 
* Adding descriptive files to repositories (README.md)
* Adding files to a repository
* Making changes to a file and committing the changes
* Creating a pull request 
* Resolving conflicts and merging pull requests
* Organizing task timelines by raising issues and creating projects.
* Forking repositories 
* Watching other users' repositories to receive updates concerning any recent activity or changes committed

I was first introduced to the GitHub Graphical User Interface after which I adopted the concept of using Git as a version control language from the command line.
I have primarily used Git for cloning repositories to my local directories, editing files, adding and commiting the files and pushing them back to the remote based
repository. However, I have experienced some challenges when using Git especially for resolving conflicts which is a key procedure that arises in version control.
To note is that learning Git and GitHub allowed me to silmutaneously learn markdown referencing as the principal text format that is used for file editing.

## Understanding Genomic Data Management and Open Science :open_file_folder:
Managing genomic data is the basis of all bioinformatics and computational biology workflow development. Being able to organize your data in a way that allows one
to efficiently carry out downstream analysis is a discipline that I learnt and have been using in the pipelines I have developed so far. Firstly, I usually leave my
raw data as raw and if need be, I ensure that I have three back-up sets of the raw data in case of any disparities, as it happened during the 16S data accreditation
process. I have also practised adding metadata to any data file of ambiguous origin which aids in keeping track of the dataset. In summary, the three facets of
managing and storing genomic data which I have utilized so far include:
* Ensuring that data used is accessible to other members
* Ensuring that original data is backed up redundantly
* Most importantly, always leaving the raw data raw!

Moreover, the concept of reproducibility in Bioinformatics was also shared which allows for other users or members to access your workflow and data so as to engage
with the same for their own research needs. Reproducibility involves designing the research study using project management plans, collecting and analyzing data using
programming and version control tools and workflow platforms such as Snakemake and Galaxy and finally publishing and making work accessible to others.

## Computational methods for biological data analysis :computer:
This involves programming techniques that are utilized for pipeline development which serves to analyse a particular type of biological data so as to make inferences
based on the same. While in the incubation program, I have been exposed to bash scripting in a UNIX environment, Python scripting, R for statistical analysis,
Nextflow as a workflow language and Galaxy for workflow development.
 
### Linux and Unix for Bash scripting 
I am currently able to efficiently create, manipulate and navigate through directories and files in a Linux environment from the command line. Furthermore, 
I have a good foundation in Bash scripting notably in using conditional statements to develop programs that are specified to a particular task. Solving bash exercise
such as this [one](https://github.com/simeonhebrew/Code-Exercises) helped me in expanding my bash syntax vocabulary. However, I have experienced a challenge in 
fully understanding how to use ```sed``` and ```awk``` for string and file manipulation using regular expressions which I am working on on a daily basis.
Moreover, I have practised Bash scripting regularly and learnt other bash scripting functionalities by following different tutorials and developing test pipelines. 
For instance,while developing the [ChIP-Seq pipeline](https://github.com/simeonhebrew/ChIP-Seq-Analysis-Pipeline), I learnt how to utilize Bioinformatics tools 
from the command line which I had previously used at GUI level eg. ```meme```. I am always seeking to expand my command vocabulary by striving to learn two commands 
a day and trying to use them while engaging in practical work.

### Python 
I have also been able to understand the basic principles of Python such as learning string manipulation, control flow statements, functions,
reading files, using modules and scripting.Jupyter notebooks which allowed for interactive python programming and referencing. This founding concepts 
enabled me to learn simple data analysis using ```pandas```.This facilitated learning basic concepts of machine learning such as supervised learning using 
modules such as ```scikit learn``` , ```matplotlib```, ```mglearn``` and ```pandas ```; my machine learning progress is available [here](https://github.com/simeonhebrew/Bioinformatics-Internship/blob/main/Machine%20Learning.ipynb). 
My most significant experience with Python has been utilizing the Biopython module for reading and parsing through sequences and performing biologically 
revelant operations such as transcribing, back-transcribing and translating sequence files.I have also been able to carry out sequence alignment, motif discovery
and accessing the NCBI's Entrez database. To practise all that had been acquired, I followed a COVID-19 protein analysis tutorial that showed how a pipeline can
be developed using the different functions of Biopython.
I also tested my competence by attempting a Biopython [exercise](https://github.com/simeonhebrew/Bioinformatics-Internship/blob/main/Biopython%20Solutions.md) where 
I was able to tackle majority of the problems.

### R 
I also embarked on learning R since it allows for relatively simple statistical analysis and also has packages for developing Bioinformatics pipelines.
Learning R was a self-paced journey where I started off with learning how to create and manipulate variables and vectors after which I went into creating and 
manipulating data frames.This allowed me to follow through querying and manipulating data from files using dedicated packages such as ```dplyr``` and ```tidyr```.
This was followed by data visualization using ```ggplot``` to generate different types of statistical plots. This was mostly accomplished using an online tutorial
offered by the Wellcome Genome Campus Courses and Certification program.
Furthermore, I was able to equip my R skillset by helping in the development of a DADA2 Pipeline for 16S rRNA microbial data analysis. It enabled me to expand my 
R syntax vocabulary and I was also exposed a wide variety of libraries that are suited for different operations. However, high level of competence would need more
tutorials and learning especially in statistical analysis of biological datasets and being able to understand and draw valid conclusions from statistical plots.

### Nextflow 
The 16S rRNA microbial data  accreditation process necessitated the learning of a workflow language for workflow developemnt of the analysis pipelines that had been 
constructed. Hence, I managed to learn the Nextflow language over a short period of time while converting a designated part of the ```qiime``` pipeline. 
This involved an introductory session on the normal syntax and flow of the workflow language after which I was able to self-learn the new DSL2 syntax that was adopted.
 The major challenge faced while learning Nextflow was comprehending the Java-based Groovy syntax since Nextflow is supported by the Groovy language. This is what I 
would like to explore so that I develop competence in Groovy scripting and resultantly in Nextflow workflow scripting.

## Galaxy 
Galaxy is also a workflow platform that I learnt during the Galaxy Smogarsbord Training Program. There is a detailed report of the Galaxy workflows that I managed to
develop [here](https://github.com/simeonhebrew/Bioinformatics-Internship/blob/main/Galaxy%20Training%20Report.md) 
I have recently attended a Galaxy for Proteomics workshop that was based on how to efficiently utilize the designated protein analysis such as 
PeptideShaker and MaxQuant the proteome workflow Galaxy instance. I am in the process of replicating the ChIP-Seq analysis pipeline on Galaxy so as to compare the 
output especially at peak calling and motif discovery level.

## HPC 
High Perfomance Computing was also introduced as an essential platform that allows one to access a variety of tools and silmutaneously reducing the runtime of running
processes and pipelines, hence scaling up the process by which data is analyzed. The HPC platform also provides a wide range of tools that allows one to carry out 
different analysis tasks in the same environment but also allows one to set up a conda environment so as to download different tools for personal use. 
I learnt how to load modules for use in the HPC Linux workspace environment as well as moving and copying files from the HPC environment to the local space and 
vice versa. I was able to utilize other HPC dedicated resources such as R (especially for the 16S accreditation process) and JupyterLab which are also hosted.

## Understanding principles of bioinformatics 
I also went through sessions where the key concepts of bioinformatics were introduced so as enhance our understanding on handling biological data.
The areas covered included;
### Biological databases 
Primary, Secondary and Tertiary databases for retrieving bioloical databases.
### Sequencing Techniques 
Sanger sequencing, Next Generation Sequencing(Roche 454 Sequencing -Pyrosequencing), Illumina Sequencing, PacBio Sequencing, Ion Torrent Technology),
Nanopore Technology
### NGS Read alignmentAlignment 
Pre-alignment file formats, Alignment methods(local alignment and global alignment), Aligners(samtools, BWA-MEM, bowtie), Alignment output file formats (SAM and
BAM file fomart), Alignment viewers (IGV, samtools, UCSC)
### Phylogenetics analysis 
Understanding traits, phylogeny, evolutionary models and divergence that occurs among organisms with time.

## 16S rRNA accreditation process 
I participated in the development of a 16SrRNA workflow for H3ABionet Accreditaton. My designated role was helping creation, modification and testing of a pipeline 
for phylogenetics and data visualization using alpha diversiy and beta diversity analysis as well as the development of a DADA2 pipeline collaboratievly using R 
For phylogenetics and data visualization, I used the ```Qiime``` tool and was able to generate significant conclusions from the same. 
The Nextflow script for phylogenetic analysis can be found [here](https://github.com/mbbu/16S_Accreditation/blob/main/Qiime2_Nextflow/modules/old_artifacts.nf) and 
the visualization script is available [here](https://github.com/mbbu/16S_Accreditation/blob/main/Qiime2_Nextflow/modules/visualization.nf).
The ```DADA2``` pipeline was key in comparing output obtained to the ```Qiime``` pipeline in terms of ASVs (Amplicon Sequence Variants) identified which would
help in estimating the bacterial species in the sample under analysis. 
The [pipeline](https://github.com/mbbu/16S_Accreditation/blob/main/Dada2_Pipeline/dada2_pipeline.R) used various R packages including the 'dada2' package which
offers a thorough sample inference algorithm for discovering true ASVs. The [report](https://github.com/mbbu/16S_Accreditation/blob/main/Dada2_report.md) of the
pipeline provides a procedural description of the pipeline as well as tabular and image output from the analysis.


# Mini-Project
I had the opprotunity of applying my skillset in a real study that involved bioinformatics analysis. This was when we (my colleague Rose Wambui and I) were tasked with
developing a variant calling pipeline as a part of a genotyping study involving comparing genotypic differences between T.congolese present in wildlife and livestock.
We approached the designated project by first going through revelant literature which described the importance of variant calling and its significance in inferring population
variation as well as transmission events. We also made ourselves aware of the various variant calling tools that are available and the algorithmic moels they utilize to discover
polymorphisms.

Background research allowed us to settle on three tools : Bcftools, Freebayes and the Genome Analyis Toolkti (GATK). We then moved to compare these tools using a sample Escherichia coli dataset so as to obtain a measure of the discrepancies that arise with respect to the number and type of variants called. Comparison indicated that GATK was a 
better suited variant calling tool for short variant discovery possibly due to its haplotype realignment algorithm. We then learnt the features that it provides and how to optimize our workflow since GATK was initially developed to cater for human variant calling. Optimization involved creating our own file of known variants which are required
for base recalibration as well as hard-filtering our raw variants since the recommended variant quality score recalibration process utilizes human HapMap data which is unavailable for non-human data, as was in our case.

We then proceeded to annotate the variants using snpEff and were able to infer sensible conclusions based on the annotation results and the metadata that was provided.
The entire [pipeline]() was developed using the Nextflow workflow language and a comprehensive [report]() on the methodology and findings is also available.





