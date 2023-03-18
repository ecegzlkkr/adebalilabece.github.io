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
A few rows from a BED file are shown below as an example:

![image](https://user-images.githubusercontent.com/70514969/226106200-eddddb86-1eb8-44f7-969f-984acc797f92.png)

###Sample Genome File 

To be comphrended which genomes are supported in SnpEff by running the following command:
```sh
$ java -jar snpEff.jar databases
```
In order to get a prebuilt SnpEff database to be downloaded and installed manually, the easiest method is to use the `download` command. For instance, the following command can be used to install the SnpEff database for the human genome:
```sh
$ java -jar snpEff.jar download -v GRCh38.105
```
> Note:  Here you should choose the one that is compatible with your VCF file, taking into account the version of your `.genome` file. Otherwise, you may get different results depending on the genome you choose.

###Sample VCF File 

One of the input files should be formatted in Variant Call Format (VCF). Genomic variants are currently stored in this format, which is used by the 1000 Genomes Project. SnpEff also uses this format by default. 

The VCF format can be summarized as being a tab-separated text file containing the following columns:

| Headers | Description |
| ------ | ------ |
| #CHROM | Chromosome name |
| POS | Position |
| ID | Variant's identifier |
| REF | Reference base(s) |
| ALT | Alternate base(s) |
| QUAL | Quality score |
| FILTER | The variant passed the quality filter |
| INFO |  A general description of the variant is provided here. Annotation information is added to this column by SnpEff. |

A few rows from a VCF file are shown below as an example:

![image](https://user-images.githubusercontent.com/70514969/226108483-bc82200a-5a60-45c3-b4c9-d41dcd3a01c3.png)

## Output file

The explanation information is added to the INFO field of the VCF file used, so that variance annotations can be examined via SnpEff. 

> In the annotation region, expressed as ANN, the variable can
> have more than one annotation, and these annotations are 
> separated by commas. In addition, each annotation is marked 
> with a "|" consists of multiple subdomains separated by
> a vertical line character.


A few rows from output.vcf file are shown below as an example:

![image](https://user-images.githubusercontent.com/70514969/226110629-5c68254f-417f-4761-91c5-211ecb5fa283.png)


>` Note` : For additional information you can follow the [SnpEff] documentation. 
>[SnpEff]: <http://pcingola.github.io/SnpEff/> 
