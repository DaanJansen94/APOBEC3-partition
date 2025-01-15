# Background
Literature indicates that an overwhelming majority of mutations found in monkeypox viral genomes are a result of deaminase editing, which provides a distinct APOBEC3 signature in the genomes. When performing evolutionary analysis of MPXV on relatively short timescales, it is therefore unlikely that a significant number of non-APOBEC3 mutations, which arise from error-prone polymerases, will accumulate. Given this, one can extract the APOBEC3 partition from the nucleotide alignment and perform phylogenetic analysis with this partition to exclude bias from artificially introduced mutations (e.g., sequencing or bioinformatics errors).

# Create APOBEC3-partition
This script takes a nucleotide alignment in FASTA format as input and automatically generates two partitions: an APOBEC3 partition and a non-APOBEC3 partition. The first partition, referred to as the "APOBEC3 partition", includes sites with putative APOBEC3 modifications, characterized by C -> T or G -> A substitutions in the relevant dinucleotide context. It also includes target sites that are fully conserved (i.e., composed entirely of C or G). All other sites in the alignment are masked as ambiguous nucleotides. The second partition serves as the complement of the first, containing all sites except those with APOBEC3 target sites, which are masked.

To run the script, navigate to the directory containing your nucleotide alignment and execute the following:

```
python apobec3_analysis.py
```
