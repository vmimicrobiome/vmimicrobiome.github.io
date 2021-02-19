Microbiome Introduction
=======================

.. figure:: ../images/microbiome_human.jpg
   :scale: 80 %
   :alt: Human Microbiome 
   
   Source: http://microbeminded.com/

A **biome** is a complex ecosystem of biological organisms, often defined and shaped by a shared ecosystem.

Therefore, a **microbiome** is a complex ecosystem of microorganisms:
    
    - Bacteria
    - Eukaryotic Fungi and Protists
    - Archaea
    - Viruses and Phages 


.. figure:: ../images/microbial_community.jpg
   :scale: 60 %
   :alt: Microbial Community
   
   Scanning electron image of a complex microbial community. *Colors are artificial.* Source: https://www.newscientist.com
   
**There are very few places on earth where microbiomes do not exist**
   
   - Deep sea vents
   - A mile underground
   - High Atmosphere
   - Middle of the ocean
   - *On* and *inside* pretty much every animal and plant (*outside of the lab*)
       
Since animals and eventually humans arose they have been ubiquitously interacting with and evolving alongside microbial communities

Definitions 
-------------------------------------------------------------------------------------------------

In popular science and among the public the term microbiome is thrown around as a **community of microorganisms**. 

Within the research community however there is more nuance (but microbiome is still used loosely), so let's clearly define some important terms:
 
    - **Microbiota** - The microorganisms forming a complex community, often charicterized using taxonomy. 
        - The bacterial component is what we will examine with **16S Amplicon Sequencing**.
        - *Who is there?*
    
    - **Microbiome** - The total genomic composition of all organisms in a *microbiota*.
        - Examined with **Metagenomic Shotgun Sequencing**. Not restricted to bacteria.
        - *What could they do?* 
    
    - **Metagenome** - The *microbiome* as captured with high-throughput genetic sequencing.
        - Captures random sections of DNA from all *microorganisms* and *macroorganisms*.
        - *What functions are available to the community?*
    
    - **Metatranscriptome** - The expressed RNA components of a *microbiome* captured with high-throughput genetic sequencing.
        - RNA is extracted, reverse transcribed, and sequenced.
        - *What are they trying to do?*
    
    - **Proteome** - The protein profile resulting from transcription and translation of the *microbiome*.
        - Often examined with mass spectrometry or sometimes NMR.
        - *What are the actively able to do?*
    
    - **Metabolome** - The profile of metabolites and biologically active chemicals.
        - The *metabolome* is shaped by enzymatic activity of the *proteome*.
        - Most often examined with targeted or untargeted mass spectrometry.
        - *How do their actions shape the abiotic environment?*

.. figure:: ../images/nesting_dolls.gif
   :scale: 100 %
   :alt: Nesting Dolls
   
   Like a nesting doll family, there are many layers that can each tell their own part of the story. Source: Giphy.communities


The Human Microbiome
-------------------------------------------------------------------------------------------------

.. figure:: ../images/microbe_human2.jpg
   :scale: 100 %
   :alt: Microbial Human 2
   
   What are the biomes of microbes on and inside the human body? Source: http://microbeminded.com/


**It is estimated that there are roughly the same number of human and microbial cells in your body!**

    - This encompases trillions of living microorganisms.
    - Surveys often report hundreds to thousands of unique bacterial species.
    - Microbiome diversity of 10 million+ unique genes, outnumbering our genetic repertoire 500:1.
    - Vast majority are along digestive tract, but skin and vagina have unique communities as well.

.. figure:: ../images/human_vs_microbial_cells.png
   :scale: 30%
   :alt: Number of Cells
   
   Estimating counts and mass of cells in the human body. Source: Sender, R. et al. *PLoS Biology*. 2016. 


**While highly abundant, microbes are much smaller than human cells.**
   
.. figure:: ../images/microbe_size.png
   :scale: 74%
   :alt: Size of Microorganisms
   
   Most microbes are 10-100x smaller than human cells (*same size as mitochondria*). Source: https://courses.candelalearning.com

16S Ribosomal DNA and Phylogenetic Markers
------------------------------------------

**So how can we look at which microbes make up a microbiota?**

The methodology we are discussing today falls under the umbrella of **Amplicon Sequencing**.

In *amplicon sequencing*, one gene shared by all microorganisms of interest is amplified and sequenced to charicterize *who is in the microbiota*?

**Amplicon sequencing involves:**
   1. Extracting all DNA from a microbial community.
   2. PCR amplifying a specific marker gene shared by the microbes of interest.
   3. Sequencing all of the PCR amplicons.
   4. Assigning the genetic sequences back to reference databases of known microbes.
   5. Compiling counts of the number of sequences representing each taxon.

This is most often done for *bacterial communities* with sections of the DNA coding region of **16S Ribosomal RNA**.

.. figure:: ../images/16s_structure.jpg
   :scale: 50 %
   :alt: 16S rRNA Structure 
   
   Secondary hairpin structure of 16S rRNA. Source: rna.ucsc.edu

**16S rRNA Structure**
   
   - The RNA component of bacteria ribosomes forms bonds between nucleotide bases.
   - The attraction of these bases forms secondary loop and hairpin structures.
   - Tertiary structure forms and combines with protein components of the ribosome to form an active unit.

.. figure:: ../images/ribosome.gif
   :scale: 180 %
   :alt: Ribosome Small Subunit
   
   30S ribosome small subunit with *16S rRNA in orange* and a number of *purple proteins*. Source: wikipedia.com

**This is a useful gene because:**
   
   - It is shared by almost all bacteria and archaea.
   - The ribosome is crucial to life
      - RNA sequence is critical for tertiary structure backbone
	  - Leads to stabilizing selection
   - For this reason it is slow evolving, particularly in regions important to the overall structure.
   - Thus it has regions that are more conserved and regions that are more variable (*evolutionary changes accrue more quickly*). 

.. figure:: ../images/16s_variable_regions.jpg
   :scale: 80 %
   :alt: 16S Variable Regions
   
   Nine variable regions are each separated by highly conserved regions. Source: biology.stackexchange.com

**16S rDNA is not the only marker gene used for amplicon sequencing, just the most common.**
    
    - Fungal communities are often targeted with the ITS (Internally Transcribed Spacer).
        - Region between the 18S and 5.8S rRNA genes in Eukaryotes. 

    - Archaea are generally targeted with different 16S primers.
        - They do not have enough homology with bacteria (captured with bacterial amplicons, but very biased).
        - Bacteria usually vastly outnumber archaea, dominating sequencing power.
        
    - I've heard of 18S and 28S being used for protists and fungi, but could really use many genes. Except...

**Keep in mind before you try to design your own amplicons...**
    
    - Many genes are not under such strict conserving selection.
        - Homology and even presence may be far more taxon restricted.
        - Harder to target because of lack of conserved regions.
        
    - PCR amplicons to a new gene or region require extensive validation.
        - May not amplify different orthologs equally, thus biasing abundance.
            - Could use mock community with known abundance as a control.

**Therefore, don't try to design your own primers unless you have a really good reason... and lots of time to validate.**
    
    - The main application would be interest in a smaller subset of taxa (i.e. betaproteobacteria class).
        - Could provide better strain resolution, but I wouldn't trust abundance.
        - Allows more reads from organisms of interest, but miss everything else.

Advantages and Disadvantages
----------------------------

**Key advantages of Amplicon Sequencing**
    
    - There are very well studied protocols, amplicons, and tools.
        
        - The `Earth Microbiome Project <http://www.earthmicrobiome.org/protocols-and-standards/>`_ protocol is the most widely accepted.
            - Very well validated, and used in many studies including the `Human Microbiome Project <https://hmpdacc.org/>`_.
            - Have protocols for 16S, 18S, and ITS detailing steps and best practices.
            
        - There are great comprehensive tools to analyze the data.
            - We will use `QIIME2 <https://qiime2.org/>`_ but `Mothur <https://www.mothur.org/>`_ is also widely used.
             
    - Generally the cheapest and most approachable method (compared to metagenomic sequencing as an alternative).
        
        - Requires less sequencing depth per sample to get confident profile.
            - This allows far more samples to be on a sequencing run.
            - In 16S we usually want 10-100k assigned sequences per sample.
            - In metagenomics 1-2 million sequences is the extreme low end, often want 10X that.
            
        - Much more computationally approachable.
            - Search against database of one gene vs all full genomes (including eukaryotic, host, viral...).
            
        - Less likely to sequence any relevant amount of human DNA.
            - Could make IRB approval easier.
            - Don't need to remove human DNA before publicly sharing, or having to restrict access to approved parties i.e. dbGAP.
                - However, if there is very little microbial DNA I have seen mostly off target sequences from human mitochondria.
            
**Key disadvantages of Amplicon Sequencing**       

    - Amplicons can only tell you who is there and in what abundance.
        - It cannot tell anything about the functional capabilities of the microbes.

    - It is semi-quantitative at best, not absolute.
        - Can really only examine relative abundance.
            - Thus never know if one sample has more or less microbes, only a microbe's ratio with other microbes.
            - No idea if changes over time are because the total number of microbes increased, decreased, or just shifted members.
            
    - Resolution is limited because the amplicons are short, so generally family or genera is the most that can be distinguished.
        - Really cannot confidently distinguish species or strains within a genus. 
            
.. figure:: ../images/amplicon_alignment.png
    :scale: 120 %
    :alt: amplicon alignment           

    Aligning short reads means there may be very few differences to distinguish related taxa. Source: nature.com


    - 16S rRNA gene copy number can vary by an order of magnitude between bacterial species.
        - The databases try to correct for this, but it's not perfect.
        - This means there is some bias in the relative abundance of members.

.. figure:: ../images/rrna_copy_number.png
   :scale: 100 %
   :alt: rRNA copy number 
        
   Most bacteria have two or more copies of rDNA in their genomes, which must be corrected for when counting totals. Source: researchgate.net


    - Seeing DNA in a sample does not confirm that there are live microbes, just that their DNA was present.
    - 
### Exporting QIIME Feature Tables
In order to proceed with downstream analysis in [MicrobiomeAnalyst](https://www.microbiomeanalyst.ca/), we will need to export our feature table, taxonomic assignments, and phylogenetic tree. We do this using the QIIME2 tools command.

Feature tables and taxonomy are exported in [BIOM format](https://biom-format.org/).
```javascript
qiime tools export --input-path paired_end/2_1_dada2_table.qza \
  --output-path paired_end/exported
qiime tools export --input-path paired_end/3_4_assigned_greengenes_94_taxonomy.qza \
  --output-path paired_end/exported
```
We then need to quickly manually edit the header of the taxonomy file to match the BIOM software format. We will make a copy and then edit the copy (just in case something goes awry)
```javascript
cp paired_end/exported/taxonomy.tsv paired_end/exported/biom-taxonomy.tsv
```
Change the first line of the header in the biom-taxonomy.tsv file to read:
```javascript
#OTUID  taxonomy  confidence
```
*Note: this header is case sensitive.*

Now we can add the taxonomy to the .biom file .
```javascript
biom add-metadata -i paired_end/exported/feature-table.biom -o /paired_end/table-with-taxonomy.biom \
  --observation-metadata-fp paired_end/exported/biom-taxonomy.tsv --sc-separated taxonomy
```
Finally, we need to export the phylogenetic tree for downstream phylogenetic analyses.
```javascript
qiime tools export --input-path paired_end/3_3_dada2_tree.qza \
  --output-path paired_end/rooted_tree.tre
```
### Concepts of Community Analysis
**How can we examine microbial communities?**

Let's switch datasets and look at: [The American Gut Project (AGP)](https://microsetta.ucsd.edu/about/american-gut-project/)
![AGP1](https://microsetta.ucsd.edu/wp-content/uploads/2019/06/american-gut-project-logo-rgb.png)

**Why?**
* Clustering features creating a phylogeny, and assigning taxonomy are the most computationally intensive
  * We used a very small and sparse dataset
  * This subset of the AGP has 1,375
  * There are 5,591 features (bacteria) and ~200 metadata measurements

* We are moving into [MicrobiomeAnalyst](https://www.microbiomeanalyst.ca/) for this section, so we need to start with preprocessed data.

![MicrobiomeAnalystBanner](https://www.microbiomeanalyst.ca/MicrobiomeAnalyst/resources/images/microbiome_opt.png) **MicrobiomeAnalyst**

We are moving from QIIME2 into an web-based graphic user interface (GUI) for data analysis. We love QIIME2 and QIIME2 has move flexibility in some ways, but MicrobiomeAnalyst has several advantages:

* Ease of use - GUIs are more user friendly than command line code
* Integration of multiple different programs
  * QIIME2 is one of 16S analysis programs, MicrobiomeAnalyst pulls in analyses from multiple
  * Shotgun metagenomic data analysis options
* Written in R
  * For those of you familiar with R, you can export the MicrobiomeAnalyst code and customize the analysis or graphs

#### Importing data into MicrobiomeAnalyst
1. Go to https://www.microbiomeanalyst.ca/ in your favorite web browser. On the home page, click on the red "Marker Data Profiling (MDP)" bubble.

![MA homepage](/images/MA_home_screen.png)

2. We are going to upload the files from the american_gut folder you downloaded prior to the workshop. We have provided the feature table in BIOM format, so click on the "BIOM format" dropdown to access the correct upload selections. Select "Choose File" and navigate to the american_gut folder on your computer and upload the .biom, .txt, and .tre files. Select QIIME for the taxonomy label type. Your screen should look like this:

![MA import](/images/import_screen.png)
*Note: MicrobiomeAnalyses has different requirements for metadata files than QIIME2. The first column with your sample names should have #NAMES as the header.*

Now click the yellow Submit button!

3. Double check the info provided as part of the Data Integrity Check. Does everything look like you expect? If yes, click "Proceed" at the bottom of the screen.

#### Filtering data
While we have already filtered our raw sequences to remove low-quality sequences in QIIME2, there is some additional data filtering we can do to improve the biological validity of our results. We can:
1. Filter out low count reads that are likely to be spurious sequences and sequencing artefacts
  * We can require a minimum count in order to remove features that appear rarely in our data (filtering by **abundance**). We want to make sure this minimum value isn't too high, or we will remove rare but biologically important sequences. Let's set it to 2 here.
  * We can also require a feature be present in a minimum number of samples to keep it in the dataset (filtering by **ubiquity** or **prevalence**). This allows us to remove infrequently occurring species that may skew our results. Again, this threshold shouldn't be too high or we will remove biologically important sequences. Let's use 10% here.
2. Filter out features with low variance that are likely to be PCR errors or contamination
  * We can remove features with the lowest X percentage of variance based on various metrics. This isn't commonly done, so let's set the variance filter to 0%.

![MA data filtering](/images/ma_data_filtering.png)

Click Submit and when you get this message in the upper right:

![MA ok](/images/ma_ok_message.png)

Click Proceed.

*Note: there is another table called "Sample Editor" here that allows you to exclude specific samples, in case you want to remove outliers, samples that didn't sequence well, or control samples prior to downstream analysis.*

#### Data normalization
We often need to account for uneven sequencing prior to downstream analysis. This will give us comparable measures of diversity between and among samples. We also want to either scale OR transform data (but usually not both) to normalize it prior to analysis.

We will choose to rarefy to the minimum library size to evenly sample across our dataset and use total sum scaling (equivalent to relative abundance). Select the appropriate radio buttons and click Submit. This one will take a minute...

Once you see this:

![MA data norm](/images/ma_data_norm.png)

Click Proceed.

*Note: There is a big debate in the microbiome community about what steps are best here. But it basically boils down to all rarefaction and normalization methods are just good attempts at getting microbiome data to behave in downstream models. You can read more here:*
https://microbiomejournal.biomedcentral.com/articles/10.1186/s40168-017-0237-y
https://besjournals.onlinelibrary.wiley.com/doi/abs/10.1111/2041-210X.13115
https://www.frontiersin.org/articles/10.3389/fmicb.2017.02224/full
https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003531

**Great! We are ready for downstream analyses!!** :tada: :tada:


#### Community transformation and examination
**Let's examine how our community is taxonomically distributed**
* Barplots of the taxonomic distribution of features for each sample
* These plots are based on relative abundance within a total sample
* Do not provide information about absolute microbial load

1. In the Analysis Overview screen, click on Stacked bar/area plot under the Visual exploration section.:

![MA analysis screen](/images/ma_analysis_overview.png)

2. Let's change our graph type to "Stacked Bar [Percentage Abundance]" (because we are working relative abundance data)

3. We have too many samples to look at individually, so we will need to select a metadata category next to "Merge samples to groups" to average relative abundances within groups in that category. As an example, let's choose sex.

4. Click Submit (it might be hiding behind the command history bar on the right side of your screen - you can scroll over to find it).

5. After it has finished processing, scroll down to see a barplot.

![MA barplot](/images/ma_sex_barplot.png)

6. Take a minute to select other metadata categories and see if there are any interesting differences! *Note: if you accidentally select something that is constant for all samples (ie, body_site - theses are all fecal samples), MicrobiomeAnalyst will get cranky and throw an error.*

**This is a really useful tool for examining our microbial communities***
* Just remember how relative abundance works...
  * Everything is relative to everything else!
  * One abundant microbe *decreasing* makes rarer microbes look *more* abundant
  *  One abundant microbe *increasing* makes rarer microbes look *less* abundant

#### Alpha and beta biodiversity
Rob already gave you a great overview of alpha and beta diversity prior to the workshop. You can rewatch those videos [here](https://youtu.be/CQaFT_vVQvw). Briefly, **alpha diversity** measures within-sample diversity, while **beta diversity** measure between-sample diversity. [There are many metrics (ways to measure) alpha and beta diversity.](https://forum.qiime2.org/t/alpha-and-beta-diversity-explanations-and-commands/2282) Some take phylogeny into account, while others do not. Some are based on presence/absence of microbes, and others account for abundance.

##### Alpha diversity
1. Navigate back to the "Analysis Overview" screen. Under the "Community Profiling" section, select "Alpha-diversity analysis".
2. Change the Experimental factor to "age_cat". Let's keep Chao1 (species richness accounting for abundance) as our metric for now.
3. Click Submit.
4. Tada!
![MA grouped age Chao1](/images/ma_age_chao1_diversity.png)

5. Let's try switching up the alpha diversity metric (Shannon - species richness and evenness accounting for abundance) and colors (Viridis).
![MA grouped age Shannon](/images/ma_age_shannon_diversity.png)

*Note: Over on the right in the side panel, you can download the plots that are shown in the GUI AND the result table with the calculated alpha diversity values for each sample.*

#### Beta diversity
1. Navigate back to the "Analysis Overview" screen. Under the "Community Profiling" section, select "Beta-diversity analysis".
2. Keep everything as the default (the Experimental factor should already be "age_cat", because that is what we used for alpha diversity). with 1800+ samples, building a new ordination plot will take a lot of time.
3. Scroll down to see the ordination plot!

![Bray-Curtis PCOA](/images/pcoa_age_cat_bray.png)

**Ok, but what does this plot mean?**

### Microbiome analysis and hypothesis interesting
**How do we ask the questions we are actually interested in?**
* Observations of the community are great, but don't address a hypothesis
* We can both visually and statistically draw conclusions about microbiome composition

#### Ordination and composition analysis
**First, an example: A study of the gut microbiome in melanoma patients.**
The authors looked at how patients responded to treatment and how that related to survival.
![Survival curve](/images/tumor_survival.png)
Survival of melanoma patients with response to anti-PD-1 immunotherapy. Source: Gopalakrishnan, V. et. al. Science. 2017. doi: 10.1126/science.aan4236

They also looked at the gut microbiome using an ordination plot
![Ordi plot](/images/tumor_ordination.png)
Microbiome ordination highlighting response to anti-PD-1 immunotherapy. Source: Gopalakrishnan, V. et. al. Science. 2017. doi: 10.1126/science.aan4236

##### What does this ordination show?
* Each dot represents an individual sample… a measure of their total gut community
  * They colored each dot based on whether they responded to treatment or not
* How close two dots are shows how similar their microbial communities are
  * Closer = more similar
  * Farther = less similar
* The centroids show where the middle, or average, is for responders and non-responders
  * While some individuals from each group overlap, there is clear divergence in the average for each group
* Axis 1 and 2
  * These are components of variation measuring differences across all the microbiomes
  * The percent variance explained shows how much difference in microbiomes is captured along that vector
  * These are somewhat arbitrary and are a result of the variation in the data
    * Specific to the samples and features going into the analysis
    * Tip: Do not compare between ordinations, only within an ordination!

##### Ok… but what is an ordination?
* A way of collapsing variation in complex data along vectors
  * Hundreds of samples and thousands of microbes can be drawn into two dimensions
* Each dimension captures a percentage of the total variation in the data
  * 50% of variance like above means there is a lot of difference being captured
  * In noisy data (Human Microbiome Project) 5-20% is a lot of variation to be captured by one dimension
* A really useful approach to quickly see patterns in data, however…
  * Treat these as qualitative exploratory analyses, and not quantitative of effect size
  * Information is lost when data is collapsed from N to two dimensions
  * Underlying math can be biased depending on data distributions
    * Don’t give quantitative stock to things like centroid distance

##### Here is a great example of one way things can go wrong
* Let's say there are 20 taxon in an ordination
* These taxa are linearly related with taxon 1 being the more distant from taxon 20

![Diagonal](/images/Diagonal.gif)

* However, when we plot them on an ordination plot, we don't see this relationship
  * The horseshoe effect has to do with a unimodal effect distortion in eigenvector space... a sentence that is probably best translated by a statistician

![Horseshoe](images/pca_horseshoe.gif)

#### Diversity analysis in more detail
##### Before we assessed alpha diversity between categorical groups
* What if your variable of interest in continuous?
1. Navigate back to "Alpha-diversity analysis".
2. Select a continuous variable, like "age_years".
3. Click Submit
4. Realize that MicrobiomeAnalyst has some limitations.
  * If you notice, it's still treating each numerical age as a categorical variable
  * Unfortunately, MicrobiomeAnalyst does not have the ability to do correlations between continuous variables and alpha diversity.
  * However, this is when exporting that result table becomes useful! You can take that .csv file into your stats program of choice and run a non-parametric Spearman correlation

##### Testing beta diversity across groups
1. Navigate back to "Beta-diversity analysis".
2. Examine the dropdown menu next to "Statistical method".

* There are several options
  * **PERMANOVA**: Permutational multivariate analysis of variance. Equivalent to a regression model. Robust to heterogeneity of variance.
  * **ANOSIM**: Analysis of group similarities. Similar to ANOVA, but sensitive to uneven variance.
  * **PERMDISP**: Permutational test of homogeneity of group dispersions. Let's you know if you have even variance (useful to pair with ANOSIM).

#### Community and taxonomic differential abundance analysis
**What if we are interested in features or taxa that are shifting in abundance?**

Let's statistically examine abundances across metadata categories using linear discriminant analysis (implemented in LEfSe). This allows us to identify taxa that are over or underrepresented in a given group.
1. Navigate to the "Analysis overview" screen. Under the "Comparison & classification" section, click on "LEfSe".
2. Feature table numbers are not very informative, so change the taxonomy level to Family.
3. We'll continue to use "age_cat" as our Experimental factor. Leave all other default settings as is.
4. Click Submit.

The default view is a dot plot, but you can also ask it for a Bar Plot (which sometimes is easier to parse if the metadata category has lots of levels).
![MA lefse results](/images/ma_lefse_output.png)

*There are a few other ways to look at differences in taxonomic abundance - feel free to check out Classical univariate analysis, metagenomeSeq, and RNA-seq methods during the breakout sessions.*

#### Random forest/machine learning methods
Supervised learning classifiers perform a series of analytical steps to see if you can predict the metadata group of a sample from it's microbiome profile.
* Take a subset of the dataset.
* Identify features that are consistently associated with the metadata categories of interested.
* See if the abundance of those features can predict the metadata categories of the rest of your samples.

We'll show a quick example of a Random Forest model.
1. Navigate to the "Analysis overview" screen. Under the "Comparison & classification" section, click on "Random Forest".
3. We'll continue to use "age_cat" as our Experimental factor. Leave all other default settings as is.
4. Click Submit.

![MA random forest](/images/ma_random_forest.png)

This plot is showing us that it can correctly classify a sample from an individual in their 30s or 40s ~45% of the time. But that it's not so easy to classify samples from other metadata categories. Our overal classification rate is not so hot. This analysis is super sensitive to even samples sizes, however.

Which brings us to some important notes:

**You should do a fair amount of background reading before throwing advanced statistics around!**
* MicrobiomeAnalyst (particularly the web-based version) is great for straight-forward analyses, but to go deeper you need to do the legwork.
* Don't get caught presenting results you cannot explain thoroughly!
**There are so many other options for analyses (including staying in QIIME2!), investigate but always use caution**
* The mcirobiome field as we know it is ~15 years folder
* Wild-west of statstics and assumptions, best practices are only starting to be enforced.

### Practice time!
We want you to be comfortable analyzing your data (or data a collaborator sent you) in MicrobiomeAnalyst at the end of this workshop. So! We are going to break into groups and you will go through the MicrobiomeAnalyst workflow together with the Atacama Soils dataset. This dataset can be found in the practice_dataset folder. We borrowed this dataset from [a classic QIIME tutorial](https://docs.qiime2.org/2020.11/tutorials/atacama-soils/).

**MicrobiomeAnalyst tasks**
1. Upload the data, using the BIOM format option. A couple of quick notes: 1) This dataset's taxonomy is in QIIME format (like the American Gut dataset earlier); 2) You might get an error about sample names not matching in the OTU table and metadata. You can ignore this error (most of the sample names do match, which is good enough for our purposes today).
2. Filter low prevalence and variance features. Note: you may want to use the mean abundance value filter for this very small and sparse dataset.
3. Rarefy and scale data.
4. Look at taxonomic differences (Visual exploration).
5. Investigate differences in alpha and beta diversity (Community profiling).
6. Test some hypotheses (Clustering & correlation/Comparison & classification).

**Questions to discuss amongst yourselves**
1. How do different count and variance filters influence how many features are retained?
2. Can you visually identify any taxonomic differences between transects or based on other metadata categories?
3. How does vegetation presence (or other metadata categories) affect alpha and beta diversity of the soil microbes?
4. Are any features differentially abundant based on any metadata categories? Do the different methods agree?
