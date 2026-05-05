# Env-INM-Leucine-Serine-Analysis-Scripts-iScience
Code for Manuscript ISCIENCE-D-26-00600
HIV-1 Env INM, Leucine, and Serine Analysis Scripts

This repository contains Python scripts used for manuscript-associated analysis of HIV-1 env nucleotide sequences. The scripts analyze FASTA files for immunostimulatory nucleotide motifs, CpG motifs, leucine and serine codon classes, and creates leucine codon-mutant sequence variants.

Requirements

These scripts require Python 3.

The following Python packages are required:

biopython
pandas
matplotlib
openpyxl

These can be installed using:

pip install biopython pandas matplotlib openpyxl

Input and output folder

All scripts are configured to use the following folder:

C:\Input

Before running the scripts, create a folder called Input directly on the C drive.

Place the relevant .fasta or .fas files into this folder.

All output files will also be saved to:

C:\Input

Included scripts

1. INM counting Script.py

This script counts selected immunostimulatory nucleotide motifs and CpG motifs in all .fasta or .fas files located in C:\Input.

It outputs:

C:\Input\combined_immunostimulatory_motif_analysis.xlsx

2. Leucine_Serine counting Script.py

This script counts leucine and serine codons in all .fasta or .fas files located in C:\Input.

It classifies leucine and serine codons into three categories:

1-2-stop
2-2-stop
No-stop

It outputs:

C:\Input\Leucine_and_Serine_analysis_combined.xlsx

Rows are highlighted in yellow when the nucleotide sequence length is not divisible by 3. These sequences should be checked before interpretation because they may not translate cleanly in the expected codon frame.

3. MutantVariantGeneratorCTA-10xrun.py

This script generates leucine codon-mutant sequence variants by converting all selected leucine codons to CTA.

It performs 10 independent runs.

It outputs Excel and FASTA files such as:

C:\Input\env_leucine_variants_run_1.xlsx
C:\Input\env_leucine_variants_run_1.fasta

through:

C:\Input\env_leucine_variants_run_10.xlsx
C:\Input\env_leucine_variants_run_10.fasta

Important: this script reads the first FASTA file it finds in C:\Input. Therefore, place only one FASTA file in C:\Input when running this script.

4. MutantVariantGeneratorTTA-10xrun.py

This script generates leucine codon-mutant sequence variants by converting all selected leucine codons to TTA.

It performs 10 independent runs.

It outputs Excel and FASTA files such as:

C:\Input\env_leucine_variants_run_1.xlsx
C:\Input\env_leucine_variants_run_1.fasta

through:

C:\Input\env_leucine_variants_run_10.xlsx
C:\Input\env_leucine_variants_run_10.fasta

Important: this script reads the first FASTA file it finds in C:\Input. Therefore, place only one FASTA file in C:\Input when running this script.

General usage


4. Place the relevant .fasta or .fas files in C:\Input.
5. Run the desired Python script.
6. Retrieve the output files from C:\Input.


For codon-level analyses, input sequences should be in the correct nucleotide reading frame.

The INM counting script and Leucine/Serine counting script can process multiple FASTA files in C:\Input.

The two mutant-variant generator scripts should be run with only one FASTA file in C:\Input at a time.
