---
layout: post
date: 2022-09-17 00:00:00 +0100
tags: Bioinformatics
categories: Bioinformatics
title: 'Fasta and Fastq File Formats'
---

Nucleotide sequences (DNA or RNA) are one of the most common data types to work with in bioinformatics. Depending on the use-case they are stored in a fasta or fastq formatted file.

Fasta is a simple format to record data. A record consists of two lines. The first line starts with the symbol `>`. This is followed by... basically anything. Usually different identifiers are given which are separated by `|`, but it could just as well be a place name such as Los Angeles. On the next line is the sequence of data that needs to be stored. This structure is continued for all the data. An example can be seen below.
```
> Identifier_1|Identifier_2|Identifier_3
AATTCGCGCGGATGCGCTATCAAACG
> Gene Name|Ensembl ID
GATAATTCGCGCGGATGCAAACGAATTCGCGCGGCGCTATCAAACGGCTATC
```

The fastq format uses records of four lines. The first is similar to the first line in the fasta format. It starts with `@` and is followed by an identifier, as well as other information if needed. The second line is the actual sequence again. The third line starts with `+`. This can be followed by the same identifier and information on the first line. The identifier and information on the third line is optional. The fourth and final line in a record is a string of characters representing the quality of the bases in the second line according to the [Phred scoring algorithm](https://yannickbijl.github.io/posts/phred-scores/). Naturally this line has the same length as the second one.
```
@SequenceID 
GATAATTCGCGCGGATGCAAACGAATTCGCGCGGCGCTATCAAACGGCTATC
+SequenceID
!''*(((***+))%%%++)(%%%..1***-+*''))**55CF>>>>CCCC65
```

In a sense, the fastq format is an extension of the fasta format. Though fastq is useful for your own sequencing data and raw data for sequence analysis, fasta formatted files still have an important function. Fasta formatted files are great for reference sequences, such as genomes and canonical gene sequences. These do not need quality scores as they are usually aggregates of multiple data sources to get the highest quality reference possible at the time.

Thus the fasta and fastq are similar, with some key differences, which helps in their own use-cases. Both are important in bio-informatics with your own data often in the fastq format, while references are usually in the fasta format.
