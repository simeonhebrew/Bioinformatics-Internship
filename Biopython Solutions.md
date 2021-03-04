# _BioPython_

---

Here are my attempts to this biopython [exercise](http://disi.unitn.it/~teso/courses/sciprog/python_biopython_exercises.html) as well as some functions that I
find important when handling sequences using Biopython.

1. A program that takes in two DNA Sequences, concatenates them and gives you the reverse complement.
```
   
   from Bio.Seq import Seq

   FirstSeq = Seq(input("Please enter the first sequence"))
   SecondSeq = Seq(input("Please enter the second sequence"))

  joint = FirstSeq + SecondSeq
  str(joint)

  joint.reverse_complement()
  
  ```
2. A program that takes in a DNA Sequence and gives the corresponding mRNA sequnce and protein sequence(codon translation using the
   standard genetic code.
   
   ```
   from Bio.Seq import Seq

   DNASeq = Seq(input("Please enter your DNA Sequence"))

   #Using the Standard Genetic Code
   print("Your mRNA sequence is %s" % (DNASeq.transcribe()))
   print("Your protein sequence is %s" % (DNASeq.translate()))
   
3. A program that takes in a DNA Sequence and gives the corresponding mRNA sequence and protein sequence(codon transaltion using the Yeast Mitochondrial Code)
   ```
   from Bio.Seq import Seq

   DNASeq = Seq(input("Please enter your DNA Sequence"))

   #Using The Yeast Mitochondrial Code

   print("Your mRNA sequence is %s" % (DNASeq.transcribe()))
   print("Your protein sequence is %s" % (DNASeq.translate (table = "Yeast Mitochondrial")))
   
4. A function that transcribes nucleotide sequences in a file(genbank/fasta formart)
   ```
   def filetranscribe(readfile):
    from Bio import SeqIO
    for record in SeqIO.parse(readfile, "genbank"):
        print(record.id)
        print(record.seq.transcribe())
        
5. A function that translates nucleotide sequences in a file(genbank/fasta formart) - 
   ```
    def filetranslate(readfile):
    from Bio import SeqIO
    for record in SeqIO.parse(readfile, "genbank"):
        print(record.id)
        print(record.seq.translate())
6.A program that takes in a sequence file,translates it and saves the corresponding protein sequence in fasta formart(Number 10 in Exercise)
  ```
   from Bio import SeqIO

   record = (rec.translate(id="tr"+rec.id, description="Translated sequence")\
          for rec in SeqIO.parse("../Data/genbankseq.fasta", "fasta") if len(rec)>0)
   SeqIO.write(record, "../Data/trgenbankseq.fasta", "fasta")
   
```
7. A program that translates sequence files and stores them in a separate file.
   ```
   def translateandkeep(readfile,writefile):
    from Bio import SeqIO
    records = (rec.translate(id="tr_"+rec.id, description="Translated sequences") \
               for rec in SeqIO.parse(readfile, "fasta") if len(rec) > 0)
    SeqIO.write(records, writefile, "fasta")

8. A program that quickly parses through large FASTA and FASTA Qc files
   ```
   from Bio.SeqIO.FastaIO import SimpleFastaParser
   count = 0
   total_len = 0
   with open("../Data/example.fasta") as readseq:
    for title, seq in SimpleFastaParser(readseq):          #if fastq file (for title,seq,qual in FastqGeneralIterator(readseq))     
        count +=1
        total_len += len(seq)
        
        print(count)
        print(total_len)
        
   ```
9. A program that adds a numbering system to a stockholm alignment file and converts it to a phylip file

   ```
   from Bio import AlignIO

   alignment = AlignIO.read("../Data/PF05356_seed.txt", "stockholm")
   name_mapping = {}
   for i, record in enumerate(alignment):
    name_mapping[i] = record.id
    record.id = "seq%i" % i
   print(name_mapping)
   AlignIO.write([alignment], "../Data/PF05356_seed.phy", "phylip")

