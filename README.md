ABOUT
-----

RefSeq files include lots of isoforms and do not include gene names. In some cases a single isoform is sufficient and it is often useful to include the NCBI gene name.  This program chooses the first isoform (not guaranteed to be the most representatitive) and creates a defline consisting of NCBI Gene name and accession.

DEPENDENCIES
--------

- JFR-PerlModules  - https://github.com/josephryan/JFR-PerlModules


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


