
#**SnpEff** 

>The open source software for annotating SNPs in a VCF file, including amino acid changes in target locations.

Documentation: https://pcingola.github.io/SnpEff/

#**Usage**
'''SnpEff version SnpEff 5.1d (build 2022-04-19 15:49), by Pablo Cingolani
Usage: snpEff [command] [options] [files]

Run 'java -jar snpEff.jar command' for help on each specific command

Available commands:
        [eff|ann]                    : Annotate variants / calculate effects (you can use either 'ann' or 'eff', they mean the same). Default: ann (no command or 'ann').
        build                        : Build a SnpEff database.
        buildNextProt                : Build a SnpEff for NextProt (using NextProt's XML files).
        cds                          : Compare CDS sequences calculated form a SnpEff database to the one in a FASTA file. Used for checking databases correctness.
        closest                      : Annotate the closest genomic region.
        count                        : Count how many intervals (from a BAM, BED or VCF file) overlap with each genomic interval.
        databases                    : Show currently available databases (from local config file).
        download                     : Download a SnpEff database.
        dump                         : Dump to STDOUT a SnpEff database (mostly used for debugging).
        genes2bed                    : Create a bed file from a genes list.
        len                          : Calculate total genomic length for each marker type.
        pdb                          : Build interaction database (based on PDB data).
        protein                      : Compare protein sequences calculated form a SnpEff database to the one in a FASTA file. Used for checking databases correctness.
        seq                          : Show sequence (from command line) translation.
        show                         : Show a text representation of genes or transcripts coordiantes, DNA sequence and protein sequence.
        translocReport               : Create a translocations report (from VCF file).

Generic options:
        -c , -config                 : Specify config file
        -configOption name=value     : Override a config file option
        -d , -debug                  : Debug mode (very verbose).
        -dataDir <path>              : Override data_dir parameter from config file.
        -download                    : Download a SnpEff database, if not available locally. Default: true
        -nodownload                  : Do not download a SnpEff database, if not available locally.
        -h , -help                   : Show this help and exit
        -noLog                       : Do not report usage statistics to server
        -q , -quiet                  : Quiet mode (do not show any messages or errors)
        -v , -verbose                : Verbose mode
        -version                     : Show version number and exit

Database options:
        -canon                       : Only use canonical transcripts.
        -canonList <file>            : Only use canonical transcripts, replace some transcripts using the 'gene_id      transcript_id' entries in <file>.
        -interaction                 : Annotate using inteactions (requires interaciton database). Default: true
        -interval <file>             : Use a custom intervals in TXT/BED/BigBed/VCF/GFF file (you may use this option many times)
        -maxTSL <TSL_number>         : Only use transcripts having Transcript Support Level lower than <TSL_number>.
        -motif                       : Annotate using motifs (requires Motif database). Default: true
        -nextProt                    : Annotate using NextProt (requires NextProt database).
        -noGenome                    : Do not load any genomic database (e.g. annotate using custom files).
        -noExpandIUB                 : Disable IUB code expansion in input variants
        -noInteraction               : Disable inteaction annotations
        -noMotif                     : Disable motif annotations.
        -noNextProt                  : Disable NextProt annotations.
        -onlyReg                     : Only use regulation tracks.
        -onlyProtein                 : Only use protein coding transcripts. Default: false
        -onlyTr <file.txt>           : Only use the transcripts in this file. Format: One transcript ID per line.
        -reg <name>                  : Regulation track to use (this option can be used add several times).
        -ss , -spliceSiteSize <int>  : Set size for splice sites (donor and acceptor) in bases. Default: 2
        -spliceRegionExonSize <int>  : Set size for splice site region within exons. Default: 3 bases
        -spliceRegionIntronMin <int> : Set minimum number of bases for splice site region within intron. Default: 3 bases
        -spliceRegionIntronMax <int> : Set maximum number of bases for splice site region within intron. Default: 8 bases
        -strict                      : Only use 'validated' transcripts (i.e. sequence has been checked). Default: false
        -ud , -upDownStreamLen <int> : Set upstream downstream interval length (in bases)'''
