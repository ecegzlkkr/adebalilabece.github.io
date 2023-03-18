# Variant Annotation
## SnpEff
>>The open source software for annotating SNPs in a VCF file, including amino acid changes in target locations.

## Installation

How to install snpeff in linux
```sh
cd 
wget https://snpeff.blob.core.windows.net/versions/snpEff_latest_core.zip
unzip snpEff_latest_core.zip
```
SnpEFf is available via bioconda and can be easily installed via
```sh
conda install -c bioconda snpeff 
```


## Input files
There is a standard format that must be followed for the files that are used as input to SnpEff.
###For annotating selected intervals 

- BED File
- Genome File
- VCF File

###Sample BED File 

In cases were solely CDS is required by using information that are in GTF file and saving output in BED format in linux

```sh
$cat Homo_sapiens.gtf | awk '$3 == "CDS" { split($9,nine,";"); printf"%s\t%s\t%s\t%s\t%s\t%s\t%s\n",$1,$4,$5,$7,$10,$14,$36> $3.".bed"}'
```
Information in sample BED file
![image](https://user-images.githubusercontent.com/70514969/226106200-eddddb86-1eb8-44f7-969f-984acc797f92.png)



