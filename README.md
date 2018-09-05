# TESS3r_SNPs
R-markdown script for spatial population genetic structure analysis with Tess3r (v1.1.0; https://github.com/bcm-uga/TESS3_encho_sen). 

This series of R scripts imports genotype data from a .csv file with 1 column for sample ID's and 2 columns per locus for genotypes, and a file of at least one stratification scheme and sample geographic locations (latitude and longitude in decimal format), converts the data to a Gtypes object that combines the sample information with the genotypes, and then conducts several analyses from Tess3r.

Steps:
1) load genotype data and stratification schemes from .csv files.
2) Create g-types object merging the data with the selected stratification scheme
3) remove samples with no latitude or longitide data (required for TESS) and monomorphic loci (in the selected strata). A file with the list of monomorphic loci that were removed is saved.
4) summarize stratified data and output summary files for strata, loci and samples. 
5) generate a map showing the data points for the selected stratification scheme.
6) reformat the data for input to Tess; Convert the gtypes object to a structure-formatted file, then to a GENIND object, then to Tess format (numerical alleles).
7) run Tess3 for a specified range of k (one to max.k) and number of iterations.
8) output cross-validate scores for each k to infer optimal number of populations.
9) visualize admisture proportions for each K as a barplot
10) map spatial interpolation of ancestry coefficients
11) ouptut histogram of p-values for specified k (this should be modified to do for all values of k)
12) output manhattan plot to show outlier p-values for Fst
13) save all data to a rdata file.
14) knit to pdf, html or docx file.
