# drug-specificty-signal-convolution

##Goal:
This work demonstrates signal processing and filter convolution on human transcriptomic data, to screen for potential off target effects of a sequence-specific mRNA-targeting drug. The drug cleaves the mRNA at a specific location based on sequence recognition, and I wanted to measure if other sites in the human transcriptome are prone to cleaved by the potential drug, and to what extent.

##Method:
The drug was incubated at large concentration (beyond saturation) with target cell line RNA and a sample of the RNA was sequenced using NGS, after one hour, from both control and experimental groups, with three repeats each. 

 
##Sample Results:
The figure below shows the true cleavage site of the drug, that is the true drug target in the transcriptome. The positive control target cleavage site is shown in red. The X -axis is the nucleotide number, where zero marks the cleavage site. The Y-axis shows the coverage depth of each nucleotide in the sequencing analysis. The three separate lines reflect the three replicates. Compared with the negative control samples, in blue, the cleavage site is characterized by a considerable reduction in sequencing coverage, which spans ten nucleotides from the cleavage site.

![image](https://github.com/user-attachments/assets/0a149184-1454-4e3d-9aad-d2a24eb40b38)

Based on this data a filter was designed to screen the entire transcriptomic sequenced data and search for comparable reductions in coverage depth that could indicate the potential of an off-target cleavage site. The filter used a statistical and mathematical representation of the difference between the positive and negative controls, and a score was given to each nucleotide in the trascriptome based on the filter result. A score of a hundred was given to the true cleavage site and other putative cleavage sites received a relative score based on measures of coverage reduction relative to the untreated sample and correlation between the three replicates. The figure below, on the left, shows the distribution of the putative leakage sites across the human genome coordinates (X-axis) and the relative score (Y-axis) the colormap shows the density of the score. According to the filter and scoring system no putative cleavage site exists in the transcriptome, at least not in comparable coverage reduction outcomes that were measured in the true cleavage site. The figure on the right, is a better. Spacial representation of the potential cleavage sites that received a score of >50 in the human genome coordinates, where the chromosome are arranges by size in descending order from top to bottom.

![image](https://github.com/user-attachments/assets/f8c6a289-3023-4716-8300-b9ea8a6c823d)

A total of 8000 locations in the transcriptome received a score of >50. These site were computationally modeled for their ability to interact with the drug to generate and actual off-target cleavage. The deltaG axis represents the ability of the drug to interact with the RNA site, where higher values (above -20 kJ/mol) are less likely to generate and true binding between drug and sequence.  The Log(Ceq) represents the logarithmic scale of relative concentration of cleavage products at equilibrium, where higher results indicate that the products are more favorable at equilibrium that the reactant, i.e. an actual cleavage is more likely. The Hamming Distance axis shows the sequence distance between the true cleavage site and the putative site, where a higher distance score will results in a more likely cleavage site due to sequence similarities. The colorbar shows the relative score the site recieved according to the filter convolution of the transcriptomic cleavage assay sequencing data.

![image](https://github.com/user-attachments/assets/3882e060-bb9f-4ca2-bd94-fdd86b42dea1)

#Summary:
These are preliminary results showing positive indications that no potential off-target cleavage sites exists, comparable in strength to the true cleavage site of the drug, in the human transcriptome under the conditions that were measured. Naturally a more in depth investigation is required to validate these result.


