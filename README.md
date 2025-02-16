$HackBio Biocoding Internship – Stage 1 Solutions$
To tackle this task, we developed a set of R scripts for Stage 1 of the HackBio Biocoding Internship. These scripts focus on problems related to genomics and population modelling.
Project Overview
In this repository, we have implemented four key scripts:
Translating DNA sequences into protein sequences
Simulating and visualizing logistic growth curves
Determining the time required to reach 80% of carrying capacity in a logistic model
Calculating the Hamming distance between two strings
Each script is designed to handle a specific computational biology challenge, helping to analyze biological data effectively.
Installation & Setup
Installing R
If R is not already installed, it can be downloaded from CRAN.
Installing Required Packages
Some scripts require additional R packages. These can be installed using:
install.packages(c("ggplot2", "dplyr"))

Script Breakdown
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

Simulating Logistic Growth Curves
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

Finding Time to Reach 80% of Carrying Capacity
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

Calculating Hamming Distance Between Two Strings
Lastly, we implemented a script to calculate the Hamming distance between two strings—useful for comparing genetic sequences or even usernames.
How We Did It:
Adjusted string lengths to match.
Compared characters at each position.
Counted the number of mismatches.
Example:
source("hamming_distance.R")

slack_username <- "BioCoder123"
twitter_handle <- "BioDevGuy"

distance <- hamming_distance(slack_username, twitter_handle)
print(paste("Hamming Distance:", distance))  # Output: "Hamming Distance: 5"

These scripts allowed us to apply computational approaches to biological problems, enhancing both our coding skills and our understanding of bioinformatics concepts.

