ABOUT
-----

RefSeq files include lots of isoforms and do not include gene names. In some cases a single isoform is sufficient and it is often useful to include the NCBI gene name.  This program does this.

DEPENDENCIES
--------

- JFR-PerlModules  - https://github.com/josephryan/JFR-PerlModules


HumRef2015
----------
HumRef2015 was built on 7/3/15 with the following commands:
Note: protein.fa.gz was last updated 3/25/15 on NCBI FTP site
Note: gene2accession.gz was last updated 7/3/15 on NCBI FTP site
Note: Version 0.01 of build_humref_w_one_entry_per_gene.pl was used

    lwp-download ftp://ftp.ncbi.nlm.nih.gov/refseq/H_sapiens/H_sapiens/protein/protein.fa.gz

    lwp-download ftp://ftp.ncbi.nlm.nih.gov/gene/DATA/gene2accession.gz

    perl build_humref_w_one_entry_per_gene.pl --fasta=protein.fa.gz --gene2accession=gene2accession.gz > HumRef2015.fa

    gzip -9 HumRef2015.fa


