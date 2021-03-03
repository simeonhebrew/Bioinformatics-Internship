# _BioPython_

---

Here are my attempts to this biopython [exercise](http://disi.unitn.it/~teso/courses/sciprog/python_biopython_exercises.html) as well as some functions that I
find key in handling sequences using Biopython.

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
        
5. A function that translates nucleotide sequences in a file(genbank/fasta formart)
   ```
    def filetranslate(readfile):
    from Bio import SeqIO
    for record in SeqIO.parse(readfile, "genbank"):
        print(record.id)
        print(record.seq.translate())

   
