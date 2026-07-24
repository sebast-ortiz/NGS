# FASTQC & MULTIQC
To visualize the inicial and later report on the sequences quality
### To visualize the raw sequences in your folder
        cd ~/folder
        ls
### Activate the environment
        conda activate bioinfo
### Run Fastqc on the raw data
        fastqc R1.fastq.gz R2.fastq.gz
### Run Multiqc to get a unified report 
        multiqc .
#### Open the Multiqc report
        explorer.exe multiqc_report.html

# CLUMPIFY
To delete optical duplicates and improve compresion
### Run Clumpify on the raw paired-end sequences
        clumpify.sh in1=R1.fastq.gz in2=R2.fastq.gz out1=R1.dedup.fastq.gz out2=R2.dedup.fastq.gz ziplevel=9 dedupe=t

# BBDUK
To delete Ilumina adapters
### Run BBDuk on the dedup paired-end sequences
        bbduk.sh in=R1.dedup.fastq.gz in2=R2.dedup.fastq.gz out=R1.clean.fastq.gz out2=R2.clean.fastq.gz ref=adapters.fa

## Finally, run once again Fastqc & Multiqc to verify the cleaning on the sequences.
