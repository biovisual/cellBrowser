UCSC Single Cell Browser Demo
=============================

This repo contains two parts:
* a Python script that runs a gene expression matrix through Seurat and
  massages the output data into JSON
* a Javascript viewer that shows the JSON files.

There is a sample dataset in data/quakeBrainGeo1/.

A viewer was created from it with these commands:

    cd data/quakeBrainGeo1/

    ../../cbPrep matrix -e geneMatrix.tsv --log2 --skip -m meta.tsv -o ~/public_html/cbTest/ -g markerSymbols.txt -l biosample_cell_type

    ../../cbPrep html -o ~/public_html/cbTest

Requirements: Seurat 1.4

Installation:

    echo 'export R_LIBS_USER=$HOME/R' >> ~/.bashrc
    source ~/.bashrc
    mkdir -p $R_LIBS_USER
    wget https://github.com/satijalab/seurat/archive/v1.4.0.tar.gz
    R CMD INSTALL v1.4.0.tar.gz -l $R_LIBS_USER
