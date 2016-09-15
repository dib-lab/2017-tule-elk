# Tule Elk de novo genome assembly and SNP calling

This repo contains scripts used for de novo tule elk genome assembly and SNP calling as described in [Titus' blog post](http://ivory.idyll.org/blog/2016-tule-elk-draft.html).

Software versions (also listed in [hpcc.modules](https://github.com/jessicamizzi/tule-elk/blob/master/hpcc.modules) file):

* FastQC v0.11.3
* Trimmomatic v0.30
* khmer v2.0
* bwa v0.7.7.r441
* SAMTools v1.2
* MEGAHIT v1.0.5 (installed by cloning the [github repo](https://github.com/voutcn/megahit))

Assembly steps:

1. Quality Evaluation using FastQC (no script for this, just `fastqc *.fq.gz` in the same directory as the files)
2. Trimming using trimmomatic - [interleave-to-before-asm.sh](https://github.com/jessicamizzi/tule-elk/blob/master/interleave-to-before-asm.sh) (great script name, I know)
3. Interleaving reads using khmer - [interleave-to-before-asm.sh](https://github.com/jessicamizzi/tule-elk/blob/master/interleave-to-before-asm.sh)
4. Assembly using MEGAHIT - [megahit-asm.sh](https://github.com/jessicamizzi/tule-elk/blob/master/megahit-asm.sh) (I was initially using velvet but found it too slow, but the scripts are still up)
5. Assembly evaluation using QUAST - [quast.sh](https://github.com/jessicamizzi/tule-elk/blob/master/quast.sh) (Results are available for viewing [here](https://docs.google.com/spreadsheets/d/1nhKOLVWc_VQt31xmik9_qEKK1S5U6biXARm7qJ-OCOQ/edit?usp=sharing))
