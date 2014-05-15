==========================================================
Translating nucleotide sequences into amino acid sequences
==========================================================
The first step before we can annotate the contigs with Pfam domains using
HMMER will be to translate the contigs into 

Programs used in this workshop
==============================
The following programs are used in this workshop:

    - Bowtie2_
    - `EMBOSS (transeq)`__
    - HMMER_
    - Optionally: Metaxa2_

.. _Bowtie2: http://bowtie-bio.sourceforge.net/bowtie2/index.shtml
.. __: http://emboss.sourceforge.net
.. _HMMER: http://hmmer.janelia.org
.. _Metaxa2: http://microbiology.se/software/metaxa2/

All programs but Metaxa2 are already installed, all you have to do is load
the virtual environment for this workshop. Once you are logged in to the
server run::

    source /proj/g2013206/metagenomics/virt_env/mg-workshop/bin/activate

You deactivate the virtual environment with::
    
    deactivate

NOTE: This is a python virtual environment. The binary folder of the virtual
environment has symbolic links to all programs used in this workshop so you
should be able to run those without problems.


Check all programs in one go with which
==================================================
To check whether you have all programs installed in one go, you can use ``which``
to test for the following programs::

    bowtie2
    bowtie2-build
    hmmsearch
    transeq
    blastall
    
Data and databases used in this workshop
========================================
In this workshop, we are (due to time constraints) going to use a simplified version
of the `Pfam <http://pfam.xfam.org/>`__ database, including only protein families
related to plasmid replication and maintenance. This database is pre-compiled and can
be downloaded from http://microbiology.se/teach/scilife2014/pfam.tar.gz
Download it using the following commands::

    mkdir -p ~/Pfam
    cd ~/Pfam
    wget http://microbiology.se/teach/scilife2014/pfam.tar.gz
    tar -xzvf pfam.tar.gz
    
In addition, you will need to obtain the following data sets for the workshop::

    XXX
    YYY
    ZZZ
    
HOW DO WE COPY THESE!!!??!?


(Optional excercise) Install Metaxa2 by yourself
===============================================
Follow these steps only if you want to install ``Metaxa2`` by yourself.
The code for Metaxa2 is available from http://microbiology.se/sw/Metaxa2_2.0rc3.tar.gz
You can install Metaxa2 as follows::

    # Create a src and a bin directory
    mkdir -p ~/src
    mkdir -p ~/bin 

    # Go to the source directory and download the Metaxa2 tarball
    cd ~/src
    wget http://microbiology.se/sw/Metaxa2_2.0rc3.tar.gz
    tar -xzvf Metaxa2_2.0rc3.tar.gz
    cd Metaxa2_2.0rc3

    # Run the installation script
    ./install_metaxa2
    
    # Try to run Metaxa2 (this should bring up the main options for the software)
    metaxa2 -h

If this did not work, you can try this manual approach::

    cd ~/src/Metaxa2_2.0rc3
    cp -r metaxa2* ~/bin/
    
    # Then try to run Metaxa2 again
    metaxa2 -h
    
If this brings up the help message, you are all set!
    
