# MUMmer container

Main tool : [MUMmer](https://github.com/mummer4/mummer)

Full documentation: https://mummer4.github.io/tutorial/tutorial.html & http://mummer.sourceforge.net/manual/

> MUMmer is a versatile alignment tool for DNA and protein sequences.


# Example Usage

mummer is a suffix tree algorithm designed to find maximal exact matches of some minimum length between two input sequences.
```
mummer -mum -b -c H_pylori26695_Eslice.fasta H_pyloriJ99_Eslice.fasta > mummer.mums
```
A dotplot of all the MUMs between two sequences can reveal their macroscopic similarity.
```
mummerplot -x "[0,275287]" -y "[0,265111]" --terminal png -postscript -p mummer mummer.mums
```
Like mummer, nucmer can handle multiple reference and query sequences, however this example will demonstrate the alignment of multiple query sequences to a single reference.
```
nucmer -mumreference -c 100 -p nucmer B_anthracis_Mslice.fasta B_anthracis_contigs.fasta
```
To view a summary of all the alignments produced by NUCmer, we can run the nucmer.delta file through the show-coords utility.
```
show-coords -r -c -l nucmer.delta > nucmer.coords
```
promer is a close relative to the NUCmer script. It follows the exact same steps as NUCmer and even uses most of the same programs in its pipeline, with one exception - all matching and alignment routines are performed on the six frame amino acid translation of the DNA input sequence.
```
promer -p promer_100 -c 100  H_pylori26695_Eslice.fasta H_pyloriJ99_Eslice.fasta
```
