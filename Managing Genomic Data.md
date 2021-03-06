# Genomic Data Management  :open_file_folder:

Data needs to be organized in a systematic way so that it is easier for the researcher to keep track all of the data produced from the study as well as make it possible
for collaborators to interact with the data efficiently.

I will point out three key levels of data management which are essential to the modern-day bioinformatician

- **Data tidiness**

Data should be clearly organized and structured in spreadsheets which will allow them to be successfully read through different programs.
The most important thing to note is that raw data should be left as raw data and should be never interfered with. This is because altering the raw data would mean that the
results of the study are tampered with and hence are not valid for analysis.

While using spreadsheets, all observations should be placed in their respective rows and the variables in their proper columns. THe column names should be
self-explanatory ad mutlitple elements should not be combined into one cell. The spreadsheet should be preferably saved in csv (comma separated values) format.
The metadata should be vividly explained, possibly through separate ReadMe files.

- **Documenting and organizing NGS projects**

In the case where large datasets are being used,proper planning, documenting and organizing of samples or datasets will be essential to the success of an in *_in silico_* study. 

`When sending sampels to sequencing facility`
Sample submission sheets should contain well labelled variable columns and data inputs which adhere to the naming convention.

`When retrieving data from sequencing facility`
One should go through the metadata provided as well as the exact sequence files (note the sequence platform used, the number of reads generated and the size of the reads)

`When storing data`
There are different options available but all should adhere to specific guidelines of storing data
- The data should be accessible to different lab members.
- The data should be kept in a place which is backed up redundantly.
- **The raw data should be left as the raw data**

The data can be stored using different resources such as high performance computers, hard disks as well as cloud computing platforms;
>
```
Microsoft Azure
Google Cloud
Amazon S3
Open Science Framework

```
- **Examining data on NCBI SRA Database**

NCBI [Sequence Read Archive](https://www.ncbi.nlm.nih.gov/sra) is a public resporitory where one can access archived data from a published study. The data can then be examined and compared with the results in the study. Using a specific identifier to the bioproject section of the databse, ne is able to access the sequence reads as well as the metadata for personal use.
It also has a toolkit that allows to you to submit your own data which will become publicly available.
The EMBL-EBI European Nucleotide Archive also offers a similar option which allows one to key in a particular accession number to access sequence files.
