# About

--------------------------------------------------------------------------------------
# Table of Contents

--------------------------------------------------------------------------------------
# Telomeres Shorten with Each Division
==============================================
<a name="Telomeres_Shorten_with_Age"></a>
# Telomeres Shorten with Age
Human telomeres are estimated to be 5,000 - 15,000 base pairs at birth (Sanders 2013, Blackburn 2001). The end replication problem shortens telomeres by approximately 50 bp with each round of cell division (Proctor 2002, Suda 2002, Hastie 1990). 

<a name="Simple_1_Telomere_Model_Damage_Checkpoint"></a>
#### Simple 1 Telomere Model & Damage Checkpoint
The situation is more complicated than that model. A DNA damage checkpoint will be triggered at around 5k bp. If cell cycle checkpoints are intact, the cell will senesce at around 5 kb. If oncogenic changes have occurred, the cell will divide until around 3k bp. The subtelomeric region is estimated to be between 2-4 kbp (Counter 1996). There will be genomic instability, which will lead to more mutations and eventual cell death UNLESS a telomere maintenance mechanism stabilizes the telomeres (Harley 2008, Shay 2012). 

![Harley_2008_Box1a](/Assets/Harley_2008_Box1a.jpg "Harley_2008_Box1a")


Here's that slightly more complicated model:

```r
# These variables are the starting point. The starting telomere length is 5000. 50 bp are lost / division. 
starting_length = 10000
current_length <- starting_length
bp_loss_per_division = 50
current_division <- 0
number_of_cells <- 1
mutations <- 0
dividing <- TRUE
# This simple model divides until senescence is reached. 
while(dividing) {
  # There will be 200 divisions for this case. I don't want to overwhelm the screen, so I'm limiting to #1 and #s divisible by 20.
  if(current_division == 0) {
    print(paste("There is one ", number_of_cells, " cell with a telomere length of ", current_length, " bp and ", mutations, " mutations."))
  }
  else if (current_division %% 20 == 0) {
    # Shay 2012 model uses 1 mutation / 20 divisions 
    mutations <- mutations + 1
    print(paste("There are ", number_of_cells, " cells after ", current_division, " doublings with a telomere length of ", current_length, " bp and ", mutations, " mutations."))
  }
  # cells senesce around a telomere length of 5000 bp Harley 2008 
  else if (current_length < 5000) {
    dividing <- FALSE
    print("This cell has senesced at a telomere length of 5,000 bp")
  }
  # The cells double, the telomere length is shortened by 50 bp, and the new division is initiated.
  number_of_cells <- number_of_cells * 2
  current_length <- current_length - 50
  current_division <- current_division + 1
}
```


Here are the last couple of lines of output:

```sh
[1] "There is one  1  cell with a telomere length of  10000  bp and  0  mutations."
[1] "There are  1048576  cells after  20  doublings with a telomere length of  9000  bp and  1  mutations."
[1] "There are  1099511627776  cells after  40  doublings with a telomere length of  8000  bp and  2  mutations."
[1] "There are  1152921504606846976  cells after  60  doublings with a telomere length of  7000  bp and  3  mutations."
[1] "There are  1.20892581961463e+24  cells after  80  doublings with a telomere length of  6000  bp and  4  mutations."
[1] "There are  1.26765060022823e+30  cells after  100  doublings with a telomere length of  5000  bp and  5  mutations."
[1] "This cell has senesced at a telomere length of 5,000 bp"
```

In the previous model we saw that 5 mutations occurred over 100 population doublings. I based this on an assumption from one of Jerry Shay's oncogenic models. Cellular senescence stopped the cells in my current model from developing more mutations. It is thought that 8-15 mutations are enough for a cell to become cancerous (Shay 2012).

![Shay_2012_Mutations_Cancer](/Assets/Shay_2012_Mutations_Cancer.jpg "Shay_2012_Mutations_Cancer")
==============================================


## 23 Chromosome, 23 (Combined Arm) Telomere Model
picutre of chromosome with specification of summing telomere
### Telomere:(Total Chromosome) Linear Relationship
suda 2002

### 23 (Combined Arm) Telomere Shortening

## 23 Chromosome, 46 (Individual Arm) Telomere Model
pictures of chromosomes w/ mention of individualizing them
### Telomere:(Chromosome Arm) Linear Relationship
Wise 2009
### 23 (Individual Arm) Telomere Shortening

--------------------------------------------------------------------------------------
# Telomerase Extends Telomeres

## Telomerase Acts on the Shortest Telomere
explain why this is wrong

## Telomerase Acts on the (Normalized) Shortest Telomere

### 23 (Combined Arm) Normalized Telomere Extension

### 23 (Individual Arm) Normalized Telomere Extension

--------------------------------------------------------------------------------------
# Telomeres Shorten with Mutant Telomerase

## Telomerase reverse transcriptase (hTERT)

### hTERT DNA

### hTERT RNA

### hTERT Protein

--------------------------------------------------------------------------------------

## Telomerase RNA Componenet (hTERC)

### hTERC DNA -> RNA

--------------------------------------------------------------------------------------

## Dyskerin

### Dyskerin DNA -> RNA

### Dyskerin RNA -> Protein

### Dyskerin Protein

--------------------------------------------------------------------------------------

# Other Mutations



65 dyskeratosis congenita and 127 unaffected relatives
fluow fluorescence in situ hybdiriation in peripheral blood leukocytes subest.s
lengths beow first percentile for age are very specific for dyskeratosis congenita. 
he shortest telomeres are associated with severe variants (Hoyeraal-Hreidarsson and Revesz syndromes), mutations in DKC1, TINF2, or unknown genes, and moderate or severe aplastic anemia.
lymphocytes alone and not granulocytes may suffice for clinical screening,

The slopes for lymphocytes in the patients with DC averaged minus 0.17 kb ± 0.1 (range −0.02 to 0.34) per year. After exclusion of the 3 patients with TERC mutations (NCI 6-1, NCI 6-2, and NCI 114-1), the slopes averaged −0.22 kb ± 0.07. The normal slope (based on the cross-sectional decline in the normal controls shown in Figure 3) was −0.05–0.1 kb, i.e. an annual loss of 0.05–0.1 kb and less than the value in the DC patients
predicted normal rate (approximately 0.2 kb per year compared with 0.05).18 
patients with excessive telomere attrition rates (e.g. >0.2 kb/year) may be on a more rapid trajectory towards a serious complication of this disorder.

# Alter 2012 Telomere length is associated with disease severity and declines with age in dyskeratosis congenita
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3291588/

* TIN2 			451 AA

* dyskerin 		514 AA
https://www.uniprot.org/uniprot/O60832
https://www.ncbi.nlm.nih.gov/gene/1736
dyskerin mutations http://telomerase.asu.edu/diseases.html#tr
Homo sapiens dyskeratosis congenita 1, dyskerin (DKC1), mRNA https://www.ncbi.nlm.nih.gov/nuccore/15011921
* hTR 		451 nt	
hTR diseases mutations: 
http://telomerase.asu.edu/diseases.html#tr
Homo sapiens telomerase RNA component (TERC), telomerase RNA https://www.ncbi.nlm.nih.gov/nucleotide/38176147
* hTERT 	3399 nt	1069 AA
htert human uniprot https://www.uniprot.org/uniprot/O14746
https://www.ncbi.nlm.nih.gov/gene/7015 
hTET mutations http://telomerase.asu.edu/diseases.html#tr
Homo sapiens telomerase reverse transcriptase (TERT), transcript variant 1, mRNA https://www.ncbi.nlm.nih.gov/nucleotide/109633030

# Nelson 2012 Dyskeratosis congenita as a disorder of telomere maintenance
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3208805/


* figure of shelterin tert, terc, dyskerin
* figure of stem cell HSC problems

# Kirwan 2009 Dyskeratosis congenita, stem cells and telomeres
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2686081/
