NOTE
-----

Some of the functionality of reduce_refseq was superceded by RefSeq Select (https://www.ncbi.nlm.nih.gov/refseq/refseq_select/). However, an advantage of reduce_refseq is that the definition lines are compact with the gene name (eg. HOXA10) followed by the accession number. Starting with HumRefSelect2019.fa.gz, I now use RefSeq Select as a starting FASTA file (rather than all of refseq) and use reduce_refseq to rename deflines (see HumRefSelect2019 below).


ABOUT
-----

RefSeq files include lots of isoforms and do not include gene names. In some cases a single isoform is sufficient and it is often useful to include the NCBI gene name.  This program chooses the first isoform (not guaranteed to be the most representatitive) and creates a defline consisting of NCBI Gene name and accession.

DEPENDENCIES
--------

- JFR-PerlModules  - https://github.com/josephryan/JFR-PerlModules

HumRefSelect2019
----------
- Note: Version 0.01 of reduce_refseq was used
- Using a browser went to NCBI protein (https://www.ncbi.nlm.nih.gov/protein) and enter the following query `Refseq_select[filter] AND Homo sapiens[ORGN]`. Then from the "Send To" pull-down menu chose "File" as the destination. Named this FASTA file: Hsap_refseq_select.fa

    wget ftp://ftp.ncbi.nlm.nih.gov/gene/DATA/gene2accession.gz 
    # gene2accession.gz was built on 12/2/19

    perl reduce_refseq/rename_refseq_select_defs --fasta=Hsap_refseq_select.fa --gene2accession=gene2accession.gz > Hsap_refseqelect_renamed.fa

    gzip -9 HumRefSelect2019.fa

HumRef2015
----------
- HumRef2015 was built on 7/3/15 with the following commands:
- Note: protein.fa.gz was last updated 3/25/15 on NCBI FTP site
- Note: gene2accession.gz was last updated 7/3/15 on NCBI FTP site
- Note: Version 0.01 of reduce_refseq was used

    lwp-download ftp://ftp.ncbi.nlm.nih.gov/refseq/H_sapiens/H_sapiens/protein/protein.fa.gz

    lwp-download ftp://ftp.ncbi.nlm.nih.gov/gene/DATA/gene2accession.gz

    reduce_refseq --fasta=protein.fa.gz --gene2accession=gene2accession.gz > HumRef2015.fa

    gzip -9 HumRef2015.fa


