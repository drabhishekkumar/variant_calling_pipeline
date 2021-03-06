
# Variant calling pipeline: exome and WGS

## Overview

This is a basic variant-calling and annotation pipeline developed at the 
Victorian Life Sciences Computation Initiative (VLSCI), University of Melbourne.

It is based around BWA, GATK and ENSEMBL and was originally designed for human (or similar) data. The master branch is configured for WGS data; there is an exome branch configured for variant calling in exome data.

To run the pipeline you will need Rubra: [https://github.com/bjpop/rubra](https://github.com/bjpop/rubra). Rubra uses the python Ruffus library: [http://www.ruffus.org.uk/](http://www.ruffus.org.uk/).

Usage: 
    
    rubra pipeline.py --config <your_config_file> --style {print,run,touchfiles,flowchart}

More command-line options are described in the Rubra documentation.

Specifically, to use the provided config files, you might call

    rubra pipeline.py --config pipeline_dev_config.py pipeline_stages_config.py --style print
    
If you use the provided config files, you should make sure you understand the analysis steps and that they are appropriate for your project.

If you use this code or Rubra itself in your research, please cite the poster at http://figshare.com/articles/Rubra_flexible_distributed_pipelines/895626 like so:

    Sloggett, Clare; Wakefield, Matthew; Philip, Gayle; Pope, Bernard (2014): 
    Rubra - flexible distributed pipelines. figshare. 
    http://dx.doi.org/10.6084/m9.figshare.895626

## Running on VLSCI's clusters (e.g. merri)

On merri we have a version of Rubra installed into Python 2.7.5, which you can load with

    module load python-gcc/2.7.5

To use the flowchart option you will need graphviz, which you can load with

    module load graphviz
