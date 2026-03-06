# Bacterial-Genomics 
TIME FOR ANALYSIS
Step 1: Download data.
./download_data.sh
Step 2: Perform QC on the raw reads
./qc_raw_reads.sh
Step 3: Trim reads using sickle
./trim_reads.sh
Step 4: Perform QC on the trimmed reads
 ./qc_trimmed_reads.sh

Step 5: Perform de novo assembly using spades
./assemble.sh
Step 6 : Polish the draft assembly using pilon
This is meant to improve the draft assembly. The scaffolds will be used. You can also modify the script to use the contigs and compare the result

./polish.sh
Step 7: Perform QC for both raw assembly and polished assembly
./qc_assembly.sh
Step 8: Generate draft genome by reordering contigs against a reference genome using ragtag\
./reorder_contigs.sh
Step 9: Perform a multi locus sequence typing using MLST software\
./mlst.sh
Step 10: Check for antimicrobial resistance genes using abricate\
./amr.sh
Step 11: Annotate the draft genome using prokka
./annotate.sh
Step 12: Get some statistics on the annotation.
Features such as genes, CDS will be counted and displayed. The scripts requires you to specify the folder where annotations were saved . i.e. P7741 Python should be used to run that script

 python get_annot_stats.py P7741_annotation P7741

Step 13: Generate dendogram using dREP\
./dendogram.sh

Step 14: Perform Pangenome Analysis using Roary.
Input files are gff (version 3 ) format. It is recommended to use prokka generated gff. So we generate the gffs for the files in the genome folder by reannotating with prokka. We use the get_genome_gffs script
./get_genome_gffs.sh 
