This is for EuchroGene customers.

To install:

1. get the installation file:
```
wget https://github.com/euchrogene/AdapterRemoval_bowtie2_RSEM/blob/main/Install_RNA-seq_AdapterRemofal_RSEM.sh
```

2. install the pipeline:
```
sudo bash Install_RNA-seq_AdapterRemofal_RSEM.sh
```

3. check installation
```
pipelines # This shows installed pipelines
RNA-seq_AdapterRemoval_RSEM # this will show help contents
```

# help contents:
```
________________________________________________________________________________________________

Used Tools: AdapterRemoval => Bowtie2 => RSEM

RSEM is a pipeline to calculate counts, TPM, and FPKM from genes or transcripts.
This pipeline fully automates RSEM from the build index through mapping and parsing RSEM results.
If you find any bugs, please email: bioinformatics@euchrogene.com

________________________________________________________________________________________________

The pipeline consists of building an index, running RSEM, and parsing RSEM results.
You can run this pipeline by following these methods:

1) simple run for paired-end sequences
   example: python RNA_seq_to_TPM_Bowtie2.py  \\
            -seq_path RNA-seq_data -ref_seq CDS_seq.fa -build_index 2

2) skip AdapterRemoval and run all the rest of the steps: use all options
   example: python RNA_seq_to_TPM_Bowtie2 -skip_filtering 2 \\
            -seq_path RNA-seq_data  -ref_seq CDS_seq.fa -build_index 2
            
3) run RSEM and parse RSEM results: set '-build_index' option as '1' and use all options
   example: python RNA_seq_to_TPM_Bowtie2.py -skip_filtering 1 \\
            -build_index 1 -seq_path RNA-seq_data -ref_seq CDS_seq.fa

4) only parse RSEM results: set '-parsing_only' option as '1'
   example: python RNA_seq_to_TPM_Bowtie2.py -skip_filtering 1 \\
            -seq_path RNA-seq_data -parsing_only 1 

________________________________________________________________________________________________

Usage;

-help                       show options
-skip_filtering (option)    1: no (Default, run AdapterRemoval), 2: yes (skip filtering)
-build_index    (option)    1: no (default), 2: yes
-ref_seq        (required)  ref seq file name (index file name must be the same as ref seq name)
-seq_path       (required)  folder path that contains RNA-seqs (compressed file can be used)
-paired         (option)    1: paired-end (default), 2: single-end 
-parsing_only   (option)    1: run all steps (default), 2: parsing the RSEM results only
-target         (option)    1: transcripts including isotypes, 2: representative genes (default is 1)
-cores          (option)    number of cores for RSEM (default is 32)
______________________________________________________________________________________________
"""
```



