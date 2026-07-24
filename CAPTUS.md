## ASSEMBLE DE NOVO
Assemble clean Ilumina reads de novo to reconstruct contiguous sequences
### Captus assemble
    captus assemble -r R1_clean.fastq.gz R2_clean.fastq.gz --min_count 5 --min_contig_len 200 --threads 6 --concurrent 1 --disable_mapping --min_contig_depth 0 -o captus_assembly

## EXTRACTION
Searches the assembly for homologous sequences and extracts target loci using reference sequences
### Captus extraction
    captus extract -a captus_assembly -n References.faa -o extractions  --threads 8 --concurrent 2 --ignore_depth
