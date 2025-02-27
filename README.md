**HackBio Biocoding Internship – Stage 1 Solutions**

We developed a set of R scripts for Stage 1 of the HackBio Biocoding Internship to tackle this task. These scripts focus on problems related to genomics and population modelling.

**Project Overview**

In this repository, we have implemented four key scripts:
Translating DNA sequences into protein sequences
Simulating and visualizing logistic growth curves
Determining the time required to reach 80% of carrying capacity in a logistic model
Calculating the Hamming distance between two strings
Each script is designed to handle a specific computational biology challenge, helping to analyze biological data effectively.

**Installation & Setup**

Installing R

If R is not already installed, it can be downloaded from CRAN.
Installing Required Packages
Some scripts require additional R packages. These can be installed using:
install.packages(c("ggplot2", "dplyr"))

**Script Breakdown**

Translating DNA to Protein Sequences

One of the tasks involved converting a DNA sequence into a protein sequence using the standard genetic code.

How We Did It:

Took a DNA sequence as input.
Split it into codons (triplets).
Mapped each codon to its corresponding amino acid.
Returned the translated protein sequence.
Example:
source("dna_to_protein.R")

dna_sequence <- "ATGGCCATTGTAATGGGCCGCTGAAAGGGTGCCCGATAG"
protein <- dna_to_protein(dna_sequence)
print(protein)  # Output: "MAMIVMGRAKGA*"

**Simulating Logistic Growth Curves**

Another task was to simulate logistic growth and visualize the results.

How We Did It:

Used a logistic growth model to simulate population dynamics.
Introduced variability in growth phases.
Generated growth curves for 100 populations.
Plotted a subset of these curves to visualize trends.
Example:
source("logistic_growth.R")

growth_data <- generate_growth_data(100)
head(growth_data)  # View first few rows

**Finding Time to Reach 80% of Carrying Capacity**

To better understand population growth, we calculated the time it takes to reach 80% of the carrying capacity (K).

How We Did It:

Simulated logistic growth over time.
Identified the time point where the population first reached 80% of K.
Example:
source("time_to_80_percent.R")

time <- seq(0, 50, 1)
growth_curve <- simulate_logistic_growth(time)
time_80 <- time_to_80_percent(growth_curve)

print(paste("Time to reach 80% of K:", time_80))

**Calculating Hamming Distance Between Two Strings**
Lastly, we implemented a script to calculate the Hamming distance between two strings, which was helpful in comparing genetic sequences or usernames.

How We Did It:

Adjusted string lengths to match.
Compare characters at each position.
Counted the number of mismatches.
Example:
source("hamming_distance.R")

slack_username <- "BioCoder123"
twitter_handle <- "BioDevGuy"

distance <- hamming_distance(slack_username, twitter_handle)
print(paste("Hamming Distance:", distance))  # Output: "Hamming Distance: 5"

These scripts allowed us to apply computational approaches to biological problems, enhancing both our coding skills and our understanding of bioinformatics concepts.



**HackBio Biocoding Internship - Stage 2 Solutions** 

This repository contains our solutions for Stage 2 of the HackBio Biocoding Internship, all implemented in R. Each task includes a brief explanation along with the R code used to solve it.  

1. Microbiology Task  

In this task, we analyzed a microbiology dataset containing Optical Density (OD600) measurements over time for different bacterial strains under two conditions:  

- Knock-out (-): A gene is deleted or inactivated.  
- Knock-in (+): A gene is inserted or activated.  

Objectives:  
- Plot growth curves (OD600 vs Time) for different strains.  
- Compare knock-out (-) and knock-in (+) strains.  
- Determine the time taken to reach carrying capacity.  
- Create scatter and box plots for carrying capacity times.  
- Perform statistical analysis to compare the two groups.  

Approach:  
1. Load and preprocess the dataset.  
2. Generate growth curves using ggplot2.  
3. Use logistic growth modeling to determine carrying capacity times.  
4. Create scatter and box plots for comparisons.  
5. Perform statistical tests (e.g., t-tests) to analyze differences.  



2. Botany and Plant Science Task  

This task required analyzing a dataset where scientists engineered mutants in a crop to improve pesticide resistance. They measured metabolic responses in wild-type (WT) and mutant plants at 8 and 24 hours, comparing them to a DMSO (control) treatment.  

Objectives:  
- Calculate the difference in metabolic response (ΔM) for WT and mutant plants.  
- Create a scatter plot for ΔM.  
- Fit a reference line (y = x).  
- Compute residuals and categorize metabolites.  
- Highlight significant metabolites and analyze their trends.  
- Plot metabolic response over time for selected metabolites.  

Approach:  
1. Load and inspect the data.  
2. Compute ΔM (Difference in Metabolic Response).  
3. Create a scatter plot comparing WT vs. Mutant ΔM.  
4. Fit a reference line (y = x).  
5. Compute residuals and categorize metabolites.  
6. Highlight significant metabolites and analyze their trends.  
7. Create a line plot for selected metabolites.  



3. Biochemistry and Oncology Task  

For this task, we explored the impact of amino acid mutations on protein function and stability using two datasets:  

1. SIFT Dataset (Functional Impact): Measures how amino acid substitutions affect protein function.  
   - SIFT Score < 0.05 → Deleterious mutation.  
2. FoldX Dataset (Structural Impact): Measures how substitutions impact protein stability (energy changes in kCal/mol).  
   - FoldX Score > 2 kCal/mol → Deleterious mutation.  

Objectives:  
- Merge SIFT and FoldX datasets using a common identifier.  
- Identify mutations affecting both structure and function.  
- Determine which amino acid has the highest impact.  
- Generate a frequency table and visualize amino acid impacts.  

Approach:  
1. Load and inspect the datasets.  
2. Create a Protein_AminoAcid column.  
3. Merge the SIFT and FoldX datasets.  
4. Filter deleterious mutations.  
5. Extract the first amino acid from each mutation.  
6. Generate a frequency table.  
7. Visualize amino acid impacts using bar and pie charts.  
8. Identify the amino acid with the highest impact.  
9. Analyze amino acids with more than 100 occurrences.  



4. Transcriptomics Task  

In this task, we worked with RNA-seq data, where gene expression changes were measured as Log2 Fold Change (Log2FC), with p-values indicating statistical significance. The dataset compares a diseased cell line to the same cell line treated with compound X.  

Objectives:  
- Generate a volcano plot for gene expression.  
- Identify upregulated and downregulated genes.  
- Investigate the biological functions of the top differentially expressed genes.  

Approach:  
1. Load the dataset.  
2. Generate a volcano plot.  
3. Identify differentially expressed genes.  
4. Investigate their biological functions.  



5. Public Health Task  

This task involved analyzing the NHANES dataset, a public health dataset from the CDC, containing survey responses, medical examinations, and laboratory test results from a representative U.S. population sample.  

Objectives:  
- Handle missing values in the NHANES dataset.  
- Visualize distributions of health metrics.  
- Calculate basic statistics (mean, variance, standard deviation, range).  
- Explore relationships between variables using scatter plots.  
- Perform t-tests to assess statistical significance.  

Approach:  
1. Load the dataset.  
2. Handle missing values.  
3. Visualize data distributions using histograms.  
4. Compute summary statistics (mean, variance, standard deviation, range).  
5. Explore variable relationships using scatter plots.  
6. Perform t-tests to analyze statistical differences.  


