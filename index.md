# Welcome to the VMI Microbiome Workshop Day 1!

![VMI](https://news.vanderbilt.edu/files/Vanderbilt-Microbiome-Initiative-banner.jpg)

Introducing the Microbiome
-------------------------------------------------------------------------------------------------

A **biome** is a complex ecosystem of biological organisms, often defined and shaped by a shared ecosystem.

Therefore, a **microbiome** is a complex ecosystem of microorganisms:

* Bacteria
* Eukaryotic Fungi and Protists
* Archaea
* Viruses and Phages


![Human Microbiome2](/images/microbial_community.jpg)

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

* **Microbiota** - The microorganisms forming a complex community, often characterized using taxonomy.
  * The bacterial component is what we will examine with **16S Amplicon Sequencing**.
  * *Who is there?*


* **Microbiome** - The total genomic composition of all organisms in a *microbiota*.
  * Examined with **Metagenomic Shotgun Sequencing**. Not restricted to bacteria.
  * *What could they do?*


* **Metagenome** - The *microbiome* as captured with high-throughput genetic sequencing.
  * Captures random sections of DNA from all *microorganisms* and *macroorganisms*.
  * *What functions are available to the community?*


* **Metatranscriptome** - The expressed RNA components of a *microbiome* captured with high-throughput genetic sequencing.
  * RNA is extracted, reverse transcribed, and sequenced.
  * *What are they trying to do?*


* **Proteome** - The protein profile resulting from transcription and translation of the *microbiome*.
  * Often examined with mass spectrometry or sometimes NMR.
  * *What are the actively able to do?*


* **Metabolome** - The profile of metabolites and biologically active chemicals.
  * The *metabolome* is shaped by enzymatic activity of the *proteome*.
  * Most often examined with targeted or untargeted mass spectrometry.
  * *How are their actions shape the abiotic and biotic environment?*

![Human Microbiome3](/images/nesting_dolls.gif)

   Like a nesting doll family, there are many layers that can each tell their own part of the story. Source: Giphy.communities


The Human Microbiome
-------------------------------------------------------------------------------------------------

![Human Microbiome3](/images/microbe_human2.jpg)

   What are the biomes of microbes on and inside the human body? Source: http://microbeminded.com/


**It is estimated that there are roughly the same number of human and microbial cells in your body!**

* This encompasses trillions of living microorganisms.
* Surveys often report hundreds to thousands of unique bacterial species.
* Microbiome diversity of 10 million+ unique genes, outnumbering our genetic repertoire 500:1.
* Vast majority are along digestive tract, but skin and vagina have unique communities as well.

![Human Microbiome4](/images/human_vs_microbial_cells.png)

   Estimating counts and mass of cells in the human body. Source: Sender, R. et al. *PLoS Biology*. 2016.


**While highly abundant, microbes are much smaller than human cells.**

![Human Microbiome5](/images/microbe_size.png)

   Most microbes are 10-100x smaller than human cells (*same size as mitochondria*). Source: https://courses.candelalearning.com

16S Ribosomal DNA and Phylogenetic Markers
------------------------------------------

**So how can we look at which microbes make up a microbiota?**

The methodology we are discussing today falls under the umbrella of **Amplicon Sequencing**.

In *amplicon sequencing*, one gene shared by all microorganisms of interest is amplified and sequenced to characterize *who is in the microbiota*?

**Amplicon sequencing involves:**
   1. Extracting all DNA from a microbial community.
   2. PCR amplifying a specific marker gene shared by the microbes of interest.
   3. Sequencing all of the PCR amplicons.
   4. Assigning the genetic sequences back to reference databases of known microbes.
   5. Compiling counts of the number of sequences representing each taxon.

This is most often done for *bacterial communities* with sections of the DNA coding region of **16S Ribosomal RNA**.

![Human Microbiome6](/images/16s_structure.jpg)

   Secondary hairpin structure of 16S rRNA. Source: rna.ucsc.edu

**16S rRNA Structure**

* The RNA component of bacteria ribosomes forms bonds between nucleotide bases.
* The attraction of these bases forms secondary loop and hairpin structures.
* Tertiary structure forms and combines with protein components of the ribosome to form an active unit.

<p align="center">
  <img src="/images/ribosome.gif" alt="animated" width="600" height ="300" />
</p>

   30S ribosome small subunit with *16S rRNA in orange* and a number of *purple proteins*. Source: wikipedia.com

**This is a useful gene because:**

* It is shared by almost all bacteria and archaea.
* The ribosome is crucial to life
  * RNA sequence is critical for tertiary structure backbone
  * Leads to stabilizing selection
* For this reason it is slow evolving, particularly in regions important to the overall structure.
* Thus it has regions that are more conserved and regions that are more variable (*evolutionary changes accrue more quickly*).

![Human Microbiome8](/images/16s_variable_regions.jpg)


   Nine variable regions are each separated by highly conserved regions. Source: biology.stackexchange.com

**16S rDNA is not the only marker gene used for amplicon sequencing, just the most common.**

* Fungal communities are often targeted with the ITS (Internally Transcribed Spacer).
  * Region between the 18S and 5.8S rRNA genes in Eukaryotes.


* Archaea are generally targeted with different 16S primers.
  * They do not have enough homology with bacteria (captured with bacterial amplicons, but very biased).
  * Bacteria usually vastly outnumber archaea, dominating sequencing power.


* I've heard of 18S and 28S being used for protists and fungi, but could really use many genes. Except...

**Keep in mind before you try to design your own amplicons...**

* Many genes are not under such strict conserving selection.
  * Homology and even presence may be far more taxon restricted.
  * Harder to target because of lack of conserved regions.


* PCR amplicons to a new gene or region require extensive validation.
  * May not amplify different orthologs equally, thus biasing abundance.
  * Could use mock community with known abundance as a control.

**Therefore, don't try to design your own primers unless you have a really good reason... and lots of time to validate.**

* The main application would be interest in a smaller subset of taxa (i.e. betaproteobacteria class).
  * Could provide better strain resolution, but I wouldn't trust abundance.
  * Allows more reads from organisms of interest, but miss everything else.

Advantages and Disadvantages
----------------------------

**Key advantages of Amplicon Sequencing**

* There are very well studied protocols, amplicons, and tools.
  * The [Earth Microbiome Project](http://www.earthmicrobiome.org/protocols-and-standards/) protocol is the most widely accepted.
    * Very well validated, and used in many studies including the [Human Microbiome Project](https://hmpdacc.org/).
    * Have protocols for 16S, 18S, and ITS detailing steps and best practices.


* There are great comprehensive tools to analyze the data.
    * We will use [QIIME2](https://qiime2.org/), but [Mothur](https://www.mothur.org/) is also widely used.


* Generally the cheapest and most approachable method (compared to metagenomic sequencing as an alternative).
  * Requires less sequencing depth per sample to get confident profile.
  * This allows far more samples to be on a sequencing run.
  * In 16S we usually want 10-100k assigned sequences per sample.
  * In metagenomics 1-2 million sequences is the extreme low end, often want 10X that.


* Much more computationally approachable.
  * Search against database of one gene vs all full genomes (including eukaryotic, host, viral...).


* Less likely to sequence any relevant amount of human DNA.
  * Could make IRB approval easier.
  * Don't need to remove human DNA before publicly sharing, or having to restrict access to approved parties i.e. dbGAP.
  * However, if there is very little microbial, DNA I have seen mostly off target sequences from human mitochondria.

**Key disadvantages of Amplicon Sequencing**       

* Amplicons can only tell you who is there and in what abundance.
  * It cannot tell anything about the functional capabilities of the microbes.


* It is semi-quantitative at best, not absolute.
  * Can really only examine relative abundance.
    * Thus never know if one sample has more or less microbes, only a microbe's ratio with other microbes.
    * No idea if changes over time are because the total number of microbes increased, decreased, or just shifted members.


* Resolution is limited because the amplicons are short, so generally family or genera is the most that can be distinguished.
  * Really cannot confidently distinguish species or strains within a genus.
  * Newer primers for longer amplification regions (e.g., 16S V4-V5) allow for species-level resolution, but still not strain-level resolution

![Human Microbiome9](/images/amplicon_alignment.png)         

Aligning short reads means there may be very few differences to distinguish related taxa. Source: nature.com


* 16S rRNA gene copy number can vary by an order of magnitude between bacterial species.
  * The databases try to correct for this, but it's not perfect.
  * This means there is some bias in the relative abundance of members.
  * 16S rt-qPCR can be used to quantify the total number of 16S rRNA genes in your sample or the number of 16S rRNA genes for a specific taxonomic group of bacteria.

![Human Microbiome10](/images/rrna_copy_number.png)


   Most bacteria have two or more copies of rDNA in their genomes, which must be corrected for when counting totals. Source: researchgate.net

   _Seeing DNA in a sample does not confirm that there are live microbes, just that their DNA was present._


Experimental Design and Sample Preparation
============================================

**Key Takeaways**

**There are caveats and biases in every method**
   - Understand the biases in your methods
   - Understand how that bias will affect results

**Plan and optimize well, then stick to one protocol!**

Experimental Design
------------------------------------------------------------------

**How do I start a microbiome amplicon study? Plan ahead!**

It is particularly important to consider the details of your study before you start

* Cannot add samples later
* Cannot remove contamination after samples are collected
* Cannot add controls necessary to validate quality after sequencing
* Cannot remove bias if other factors vary with treatment of interest
* Cannot get more microbial DNA if host DNA dominates


![Human Microbiome11](/images/experimental_design_flaw.jpg)

   Source: Aaron Bacall Source: www.art.com


**Start with a question and hypothesis.**
* Consider expected effect size on microbiome composition
* Calculate how many samples will be needed to detect if the effect exists
* Consider changes community wide and detecting changes in taxon abundance and presence
* Keep in mind not every sample will pass every QC step - samples will be lost
  * Larger N
  * Parallel processing replicates

**Always step back and ask: "Will a whole community profile answer my question?"**
* Often people hypothesize that "the microbiome will change", without considering what that actually means
  * Amplicon sequencing doesn't tell you community function
  * It won't give you strain or even consistent species level resolution
    * In addition to *E. coli*, there are five other species in the genus *Escherichia* and some are commensal in the human gut

Sampling and Controls
------------------------------------------------------------------

**How will you collect your samples?**

**Generally consider in collection:**

* **Size of sample**
  * Determines available DNA
  * Can you control an equal amount from each subject - *absolute quantification*
  * Reserve sample - mix evenly so reserve is the same as utilized sample


* **Sampling vessel**
  * Ease of collection
  * Sterility
  * Stabilization solution
    * Need DNA *and* RNA
    * Other 'omics - *i.e. mass spectrometry affected by salt concentration, SCFA metabolites interact with ethanol*

![Human Microbiome12](/images/genotech_tube.jpg)

   Source: www.dnagenotek.com

* **Storage**
  * Immediate storage -80C > Storage at -20C > Storage at room temperature in >90% ethanol
  * Long term stabilization solutions can introduce bias
  * Prevent bacterial overgrowth at room temperature

**Key controls to keep in mind:**

* **Uniformity**
  * Collect samples at the same time and method across treatment groups
  * Same for processing DNA extraction and library preparation for sequencing


* **Randomization**
  * Consider many factors that could vary across treatment groups
    * Time of day, season
    * Sampling in same location
  * Mouse cage effects
    * Co-housing
    * Mixing bedding and food
  * Other factors that can influence microbiomes
    * Age, sex, reproductive status, health status, body fat percentage, recent antibiotic use, etc


* **Sterility**
  * Collect samples, but also sample microbes in the local environment if possible
  * Always include blank water samples
    * Collection blanks
    * Extraction blanks
    * Library preparation blanks
    * Sequencing blanks
  * Work in biosafety hood whenever possible
    * Particularly sensitive to contamination before PCR steps


* **Mock community**
  * Known taxonomy and abundance


* **Generous donor**
  * If sampling / extracting / sequencing in batches include one consistent sample across each

**If working with human subjects:**

<p align="center">
  <img src="images/microbe_human_teddy.gif" alt="animated" />
</p>
   Source: Charis Tsevis

   - Consider ease of self-collection
   - Different body sites have very different communities
      - Even location on a stool sample (inside versus outside)
   - Biopsies are loaded with human DNA
   - IRB compliant methods
      - Gloves
      - Way to catch stool in toilet and disposal
      - Proper instructions
   - Immediate acquisition versus returning samples later
      - Cannot control amount provided if self-collection
	  - Must stablize to prevent bacterial overgrowth, or 'blooms'

![Human Microbiome13](/images/genotech_sampling.png)

   Source: www.dnagenotek.com

DNA Extraction
------------------------------------------------------------------

**DNA extraction techniques vary significantly in community bias**

   - Every kit introduces bias, so pick one and stick with it!
      - There are many options, so research which is best for your long term goals
      - The [Earth Microbiome Project](http://www.earthmicrobiome.org/protocols-and-standards/dna-extraction-protocol/) has well documented protocols.


   - Efficiency at lysing cells is important
      - Bead beating versus chemical lysis
      - Mechanical bead beating seems to be most thorough gram +/-
      - Keep in mind bead beating heats the sample through friction, don't over-do it!
      - Heat can be your friend for difficult-to-extract samples, however


   - Take time to properly optimize and document
      - Always note extraction batch, who performed the extraction, and the kit lot number
      - Always include extraction blanks, all kits have contaminants - [kit'ome](https://bmcbiol.biomedcentral.com/articles/10.1186/s12915-014-0087-z).
      - Some kits perform dual DNA and RNA extraction

Amplification
------------------------------------------------------------------

**PCR amplification of the marker gene of interest**

   - **Use known protocols and established primers**
      - Different variable regions bias the community differently, stick to what's known!
      - The [Earth Microbiome Project](http://www.earthmicrobiome.org/protocols-and-standards/16s/) has well documented PCR protocols (*16S, 18S, ITS*)
      - Always optimize your PCR for the expected sequence length and concentration
      - Include PCR blank to control for processing contamination


   - **Sequencing Depth**
     - Generally 10k - 100k sequences per sample is adequate coverage
     - Diminishing returns at greater depths
        - Taxonomic resolution based on sequence length not sequencing depth
       - Many reads increase sequencing errors, qc filtered
       - Analyses are rarefied or relative abundance
          - Rare organisms will still be rare, depth doesn't change proportions

Earth Microbiome Project V4 Primers

515F FWD: GTGYCAGCMGCCGCGGTAA

806R REV: GGACTACNVGGGTWTCTAAT

Earth Microbiome Project V4-V5 Primers

515F FWD: GTGYCAGCMGCCGCGGTAA

926R REV: CCGYCAATTYMTTTRAGTTT

*The primer sequences in EMP protocols are always listed in the 5′ -> 3′ orientation.  This is the orientation that should be used for ordering.*

Components of full reaction:

\_\_\_\_\_5′ Illumina adapter_________________________Golay barcode_____Pad________Linker___Forward primer

FWD:  AATGATACGGCGACCACCGAGATCTACACGCT XXXXXXXXXXXX  TATGGTAATT GT      GTGYCAGCMGCCGCGGTAA

   - Each sample PCR reaction will be performed with it's own unique barcode combination
   - This allows bioinformatic demultiplexing - assigning sequences to their respective sample

Sequencing Platforms
------------------------------------------------------------------

![Human Microbiome14](/images/illumina_theory.png)

   Illumina sequencing molecular biology Source: Jaroslaw Grzadziel (Research Gate)

**Illumina MiSeq**

   - By far the most widely used sequencing method for 16S rRNA gene amplicon sequencing
      - \>5,000,000 sequences per run allow multiplexing many samples
      - High coverage of the community (~10k sequences per sample is ideal depending on complexity)


   - Short sequences up to 300bp generally cover 1-3 variable regions
      - Allows high coverage, but lose resolution past genus level
      - Paired end is better than single end, as long as your forward and reverse reads overlap

**Illumina HiSeq/NextSeq/NovaSeq**
   - Widely used sequencing method for shotgun metagenomic sequencing
   - 50-150 bp sequence reads (Not long enough for most amplicon sequencing)


**PacBio and Nanopore**
   - Can do full 16S gene
      - Very high strain level resolution
      - But *much* lower coverage and multiplexing = higher costs
      - Higher error rates


Metadata File
------------------------------------------------------------------

**How do you store all of this information about samples in a useful way?**

   - **A metadata file is composed of:**
      - Each row representing a sample
      - Each column representing some information about each sample
      - Are TSV - tab separated values
         - TSV is a .txt output format from Excel
      - A header line starting with a # indicates the column names

- There is a bit more flexibility in file structure in QIIME2, but any mapping file that worked in QIIME1 is a valid metadata file in QIIME2

![Human Microbiome16](/images/map_exp.png)
   Source: Example mapping file in excel.

* Always start with **#sampleid** column
  * A unique id for each sample - cannot be the same as any other sample


* Include columns for the unique sample **barcodes**
  * Allows demultiplexing of sequences to their respective sample


* Also include **control and qc** information about DNA extraction batch, person extracting, PCR batch, sequencing run, cage...
  * Allows testing if these factors influenced the community composition
  * Have columns indicating which samples are blanks, mock community, and generous donor samples


* Have columns for your **treatment** and any **covariates** of interest
  * Age, sex, BMI, collection season...


* Last column should be **description** if you need backward compatibility with QIIME1

For more detailed information check out the full [QIIME2 Metadata Guide!](https://docs.qiime2.org/2021.4/tutorials/metadata/)

**Best Practices**

   - Rule Number 1: Don't get fancy!
      - Don't use spaces, use _ (underscore) instead
      - Except #sampleid, the only punctuation in this column can be dashes '-' (no underscores)
      - Don't include other types of punctuation, this will only cause problems later on!

   - Leading and trailing white spaces are ignored

   - I'd stick to all lower-case (case insensitive) characters
      - Not required, but may save you a *lot* of trouble with weird errors later on!

Sampling the Mouse Microbiome
==================================================================
<p align="center">
  <img src="/images/giphy2.gif" alt="animated" width="600" height ="300" />
</p>

The objective of this lecture is to provide the attendees with an overview of factors that may influence animal experiment outcomes in microbiota research. Additionally, we will discuss the experimental approaches available to establish a causative role for the gut microbiota in disease. 

Please find the presentation being shared by Dr. Byndloss available for download [here](https://github.com/vmimicrobiome/vmimicrobiome.github.io/blob/main/images/Presentation_Bootcamp%202021.pdf) and an excellent article on *best practices for analysing microbiomes* [right here!](https://pubmed.ncbi.nlm.nih.gov/29795328/)


From Sequences to Community Composition
=================================================================

Data Source: https://github.com/vmimicrobiome/vmimicrobiome.github.io

**What to do when you get back your sequence files?**

Sequence File Formats
------------------------------------------------------------------

**What do sequence file formats look like?**

They can be displayed in a couple ways.

**The first is as two separate files for the sequences and the quality scores**

![Human Microbiome17](/images/fasta_qual_format.png)

   Fasta and quality score file formats

   - Fasta files - The genetic sequences of your amplicons

      - Header lines always starts with a '>'
         - Describes the sequence, often an id or incremental number
      - Next line is the genetic sequence of your amplicon itself (A,T,C,G's)

   - Quality score files
      - Start with the same headers as the fasta file
      - Contain scores that describe how confident the sequencer is in that particular base call
      - Often these are expressed as Phred scores:

![Human Microbiome18](/images/phred_score.png)

   Phred score translation to base call accuracy

**A second way you may find your files is a fastq file**

![Human Microbiome19](/images/fastq_format.png)

   Fastq file format

   - Fastq is essentially a combination of fasta and quality score files
      - Header lines often start with '@'
      - Followed by the genetic sequence like a fasta file
      - The third line is generally just a '+'
      - The fourth line is a condensed form of the quality scores
      - Then the pattern repeats for the next sequence

**Some sequencing centers perform some quality processing, others don't. Make sure you ask what has been done!**

   - If they try to provide another format or raw data, ask for one of these two options. This is standard.
   - Always get quality scores, even if they "did quality control for you"


Types of Sequences in QIIME2
------------------------------------------------------------------

**How do you make QIIME2 aware of your sequences and mapping file?**

![Human Microbiome20](/images/multiplexing.jpg)

   Source: Martha Park - Institute for Quantitative & Computational Biosciences Workshop

   - **QIIME2 must import all data files and convert them**
      - They become custom QIIME2 format files
      - Allows for compression to save space and allow faster access

   - **Importing sequences has lots of options**
      - Some sequencing centers may demultiplex into fastq file for each sample
      - Single versus paired end sequencing
      - Quality scores or not (if you generated the data you should have these)
      - Barcodes may be in a separate file

![Human Microbiome21](/images/qiime2_import_demultiplex.png)

   Source: QIIME2 - https://docs.qiime2.org/2021.4/tutorials/overview/#demultiplexing

**Generally importing sequences will follow this format:**

```bash
   qiime tools import \
      --type XXX \ # The format of your sequence files
      --input-path XXX \ # The folder or manifest file where sequences are located
      --input-format XXX \ # Tell QIIME2 how to import the sequences properly
      --output-path XXX # Where the processed sequences should be saved
```  

**Fastq Manifest Format**

This is the most flexible approach if the sequencing center demultiplexed your samples

**Make a manifest telling QIIME2:**
   - Which files align to which samples
   - The paths to each of those files
   - The direction: forward or reverse

**Manifest Format**
   - CSV - comma separated values in each column
   - sample-id must match the sample names in your mapping file
   - Header line must match below
   - Save as CSV file

sample-id,absolute-filepath,direction #header line

sample-1,$PWD/some/filepath/sample1_R1.fastq,forward

sample-1,$PWD/some/filepath/sample1_R2.fastq,reverse

**Phred 33 vs 64**
   - Phred scores are sometimes offset by 31, depends on sequencer software
   - This is important because they are always converted to 33 - Ask sequencing center!
   - If you can ask for 33, as the 64 can be slow to convert for large files

![Human Microbiome22](/images/phred_scores.gif)

   Phred score encoding for 64 and 33. Source: https://www.drive5.com/usearch/manual/quality_score.html

**Command options:**
```
   -input-format
      - SingleEndFastqManifestPhred33
      - SingleEndFastqManifestPhred64
      - PairedEndFastqManifestPhred33
      - PairedEndFastqManifestPhred64

   -type
      - 'SampleData[SequencesWithQuality]'
      - 'SampleData[PairedEndSequencesWithQuality]'

   -input-path
      - Path to your manifest file or folder of files

   -output-path
      - Where QIIME2 will save the processed sequences in .qza format
  ```   
Depending on your formats it will look something like:


**Example for Paired end with Phred 64**

 ```bash
   qiime tools import \
     --type 'SampleData[PairedEndSequencesWithQuality]' \ # Change for paired/single end sequences
     --input-path my_manifest.txt \
     --output-path 1_0_input_seqs.qza \
     --input-format PairedEndFastqManifestPhred64 # Change for paired/single and phred format
```
**Earth Microbiome Project format**

This is a more specific format if you follow the EMP protocols and the sequencing center does as well

A good approach if your sequences are not demultiplexed (all samples sequences together)

   - All files in fastq format - often .gz indicates GunZip compression
   - Single End:
      - Fastq file of sequences - sequences.fastq.gz
      - Fastq file of separated barcodes (by sequencing center) - barcodes.fastq.gz
   - Paired End:
      - Fastq file of forward sequences - forward.fastq.gz
      - Fastq file of reverse sequences - reverse.fastq.gz
      - Fastq file of separated barcodes (by sequencing center) - barcodes.fastq.gz

Place these files in a folder (my_seqs/), and use that folder name as the --input-path argument:


**Single End**
   ```bash
   qiime tools import \
     --type EMPSingleEndSequences \
     --input-path my_seqs \
     --output-path 1_0_input_seqs.qza
```
**Paired End**
   ```bash
   qiime tools import \
     --type EMPPairedEndSequences \
     --input-path my_seqs \
     --output-path 1_0_input_seqs.qza
```

**There are other options for inputting sequences** :
check the [QIIME2 documentation](https://docs.qiime2.org/2021.4/tutorials/importing/) if these don't fit your data


Now let's get to work and try it on some example data!!!
------------------------------------------------------------------

**Importing and Demultiplexing**

<p align="center">
  <img src="/images/giphy.gif" alt="animated" width="600" height ="300" />
</p>

First lets take a look at the mapping file to understand how QIIME2 creates visuals

```bash
   qiime metadata tabulate \
     --m-input-file paired_end/metadata.tsv \
     --o-visualization paired_end/1_0_metadata_stats
```

This will output a file 1_0_metadata_stats.qzv
   - .qzv files are QIIME2's visualization files
      - They can be opened with 'qiime tools view ...'
   - .qza files are QIIME2's data files
      - These cannot be viewed, and are often compressed
	  - Other scripts can often create visual .qzv files from .qza

**Let's see what we made**

```bash
   qiime tools view paired_end/1_0_metadata_stats.qzv
```

**To import sequences and demultiplex...**

1. You should navigate to the folder called data/
2. We will use the folder paired_end: This contains multiplexed sequence files and a metadata file
   1. Forward sequences - reverse.fastq.gz
   2. Reverse sequences - forward.fastq.gz
   3. Barcode sequences - barcodes.fastq.gz
   4. Metadata file - metadata.tsv
3. We will import the sequences into QIIME2 format
4. We will demultiplex the sequences
5. We will examine the distribution of sequences across each sample



**See the files**

```bash
   ls -lsh paired_end/raw_seqs/
   ```

   **Import the files into QIIME2 format**
   ```bash
   qiime tools import \
      --type EMPPairedEndSequences \
      --input-path paired_end/raw_seqs/ \
      --output-path paired_end/1_0_input_seqs.qza
 ```   
   **See the new output file**
   ```bash
   ls -lsh paired_end
   ```
   **Demultiplex the sequences based on barcodes in mapping file**
```bash
   qiime demux emp-paired \
      --m-barcodes-file paired_end/metadata.tsv \
      --m-barcodes-column BarcodeSequence \
      --i-seqs paired_end/1_0_input_seqs.qza \
      --o-per-sample-sequences paired_end/1_1_demultiplexed_seqs \
      --p-rev-comp-mapping-barcodes \
      --output-dir paired_end/log_files
```
  **See the new output file**
  ```bash  
   ls -lsh paired_end
  ```
  **Summarize the sequences per sample**
```bash
   qiime demux summarize \
      --i-data paired_end/1_1_demultiplexed_seqs.qza \
      --o-visualization paired_end/1_2_demultiplexed_seqs_summary.qzv
```
   **Open the summary**
```bash
   qiime tools view paired_end/1_2_demultiplexed_seqs_summary.qzv
```

Click the 'Interactive Quality Plot' tab to view Phred scores

**QIIME2 has our sequences... now what?**

**If they are paired end then we need to join them**
   - Aligns forward and reverse sequences

![Human Microbiome24](/images/pe_quality.png)

   Paired end quality scores across sequence. Source: Kwon, S. Lee, B. Yoon, S. doi: 10.1186/1471-2105-15-S9-S10

**We also need to do some trimming and filtering to remove basepairs and sequences with low quality score**

**And, we need to characterize the community**

**Note: Input and output files are named incrementally!**
  - This keeps them in order when you open in a folder
  - Allows logic flow of code and files to align
  - Keeps everything organized when you may generate hundreds of files!!!

**Keep in mind there are often more options than just the ones I am showing here...**

To view all of the parameters available in a QIIME2 script follow just the function call with --help

   **LIST ALL PARAMETERS FOR quality-filter q-score-joined SCRIPT**
  ```bash
   qiime quality-filter q-score --help
```

**For example here are all of the useful options for filtering by quality scores**
```

  --i-demux ARTIFACT_PATH         The demultiplexed sequence data to be
                                  quality filtered.  [required]
  --p-min-quality INTEGER         The minimum acceptable PHRED score. All
                                  PHRED scores less that this value are
                                  considered to be low PHRED scores.
                                  [default: 4]
  --p-quality-window INTEGER      The maximum number of low PHRED scores that
                                  can be observed in direct succession before
                                  truncating a sequence read.  [default: 3]
  --p-min-length-fraction FLOAT   The minimum length that a sequence read can
                                  be following truncation and still be
                                  retained. This length should be provided as
                                  a fraction of the input sequence length.
                                  [default: 0.75]
  --p-max-ambiguous INTEGER       The maximum number of ambiguous (i.e., N)
                                  base calls. This is applied after trimming
                                  sequences based on `min_length_fraction`.
                                  [default: 0]
  --o-filtered-sequences ARTIFACT_PATH     SampleData[JoinedSequencesWithQuality]
                                  The resulting quality-filtered sequences.
                                  [required if not passing --output-dir]
  --o-filter-stats ARTIFACT_PATH       Summary statistics of the filtering process. [required if not passing --output-dir]
  --output-dir DIRECTORY          Output unspecified results to a directory

```

DADA2 - The New OTU
------------------------------------------------------------------

![Human Microbiome25](/images/otu_traditional.png)

   Traditional Operational Taxonomic Unit (OTU) clustering

**How do we actually characterize a community?**

1. Lump similar sequences together
   - There are a variety of algorithms
      - OTUs - Sequence similarity % cutoff
      - Deblur - Identical sequences based on likelihood of being biological versus artifactual noise
      - DADA2 - Similar sequences based on likelihood of being biological versus artifactual noise

2. Assign taxonomy to each of the sequence clusters or OTUs
   - Done using reference databases of known taxon for the amplicon of interest

3. Total the counts for each cluster across each sample into observation table

**We will use DADA2. Deblur is now really the other option (don't use traditional % cutoffs).**

There are advantages and caveats to each, but they get very similar results for the most part.
  - Deblur removes sequences that are not likely biologically valid
  - DADA2 corrects sequences that are not likely biologically valid
  - Deblur requires separate commands to pair and quality-filter sequences prior to denoising
  - DADA2 pairs, trims, quality-filters, and denoises sequences all in one QIIME command

**To get DADA2 'features' we will:**
   1. Pair the sequences
   2. Evaluate the quality (Phred) scores along the sequences
   3. Trim the sequences to the same length and to remove primers
   4. Use DADA2 to 'denoise' - correct likely sequencing errors
   5. Use DADA2 to count the remaining sequences for each feature

To learn more about Deblur, [take a look at this QIIME2 tutorial](https://docs.qiime2.org/2021.4/tutorials/read-joining/)

**Let's go back to our summary plot to decide where to trim our seuqences... click the 'Interactive Quality Plot' tab**

```bash
##### INVESTIGATE THE QUALITY SCORE PLOT TO PICK TRIM LENGTHS BELOW #####
   qiime tools view paired_end/1_2_demultiplexed_seqs_summary_qc_summary.qzv
```

Note at the ends, the quality starts to dip slightly. However, the Phred score never drops below 20, so we will keep the full length read.

Where you trim on the ends is somewhat subjective, but generally pick a point where the quality drops but you still have enough overlap and make sure you change in your script!

**Let’s set the right/reverse truncation to 150bp (our sequence length) for both sequences**

Where you trim at the beginning is based entirely on your primer length. The primers in this study were both 13bp long

**Let’s set the left/forward trim to 13bp (our primer length) for both sequences**

There are many options for the next step, think about your situation

**DADA2! Lets denoise our sequences into a feature table**

   **DADA2 DENOISE DUPLICATE SEQUENCES AND CREATE OBSERVATIONS**   
  ```bash
  qiime dada2 denoise-paired \
    --i-demultiplexed-seqs paired_end/1_1_demultiplexed_seqs.qza \
    --p-trunc-len-f 150 \
    --p-trunc-len-r 150 \
    --p-trim-left-f 13 \
    --p-trim-left-r 13 \
    --o-representative-sequences paired_end/2_0_dada2_representative_seqs.qza \
    --o-table paired_end/2_1_dada2_table.qza \
    --o-denoising-stats paired_end/2_2_dada2_stats.qza

# See output files
  ls -lsh paired_end
   ```
*DADA2 can take a while to run, so take a minute to stretch your legs!*

**Now we have generated:**

   - Representative sequences: 2_0_dada2_representative_seqs.qza
      - These will be used for alignment, phylogeny building, and taxonomic assignment

   - Observation table: 2_1_dada2_table.qza
      - These are the counts for each representative sequence across each sample

   - Statistics: 2_2_dada2_stats.qza
      - Allows us to examine counts across samples

**Let's look at the stats...**

```bash
##### DADA2 VISUALIZE STATISTICS #####
  qiime metadata tabulate \
    --m-input-file paired_end/2_2_dada2_stats.qza \
    --o-visualization paired_end/2_3_dada2_stats_summary.qzv

  qiime tools view paired_end/2_3_dada2_stats_summary.qzv
```
**And summarize the table...**

```bash
##### DADA2 SUMMARIZE TABLE #####
   qiime feature-table summarize \
      --i-table paired_end/2_1_dada2_table.qza \
      --o-visualization paired_end/2_4_dada2_table_summary.qzv \
      --m-sample-metadata-file paired_end/metadata.tsv

   qiime tools view paired_end/2_4_dada2_table_summary.qzv
```
**And look at the representative sequences...**

```bash
##### DADA2 SUMMARIZE SEQUENCES #####
   qiime feature-table tabulate-seqs \
      --i-data paired_end/2_0_dada2_representative_seqs.qza \
      --o-visualization paired_end/2_5_dada2_representative_seqs_summary.qzv

   qiime tools view paired_end/2_5_dada2_representative_seqs_summary.qzv
```
**Neat! Well done!**

Alignment into Amplicon Phylogeny
------------------------------------------------------------------


![Human Microbiome26](/images/16s_phylogeny.png)

   Example phylogeny. Source: Rob Onyenwoke *et. al.* doi: 10.1007/s00203-004-0696-y

**A phylogeny depicts the genetic relatedness between each of our amplicons**
   - Used for diversity metrics incorporating genetic relatedness of features

**To construct a phylogeny of our representative sequences we will..**
   1. Align the sequences using Mafft
   2. Mask highly variable positions in the alignment (removes uninformative noise)
   3. Construct an unrooted phylogeny with FastTree
   4. Root the phylogeny at the tree's midpoint

QIIME2 has individual commands that perform each of these steps, but also has a helpful builtin pipeline that runs all of them with a single command.

```bash
##### ALIGN REPRESENTATIVE SEQUENCES, MASK NOISY POSITIONS, CREATE PHYLOGENY, ROOT PHYLOGENY AT MIDPOINT #####
   qiime phylogeny align-to-tree-mafft-fasttree \
    --i-sequences paired_end/2_0_dada2_representative_seqs.qza \
    --o-alignment paired_end/3_0_dada2_aligned_seqs.qza \
    --o-masked-alignment paired_end/3_1_dada2_aligned_masked.qza \
    --o-tree paired_end/3_2_dada2_tree_unrooted.qza \
    --o-rooted-tree paired_end/3_3_dada2_tree.qza

# look at files
   ls -lsh paired_end

```

Taxonomy Assignment
------------------------------------------------------------------

**Finally before we can start analysis we want to assign taxonomy to each of our representative sequences**
   - More biologically informative than sequences with arbitrary ids
   - Allows us to bin by known classifications

**We will use the GreenGenes 94% reference database for a minimal example, but I would suggest another database for your actual project**
   - Silva
   - GreenGenes 99%
   - [Other options, please learn which is best for your project!](https://docs.qiime2.org/2021.4/data-resources/)

**First import the GreenGenes Database**
   - 94% Unique 16S Sequences
   - Taxonomy Reference Table
      - Contains number of ribosomal DNA copies for each taxon

```bash
### IMPORT TAXONOMY REFERENCE SEQUENCES ###
   qiime tools import \
      --type 'FeatureData[Sequence]' \
      --input-path greengenes/94_otus.fasta \
      --output-path paired_end/greengenes_94_otus.qza

### IMPORT TAXONOMY REFERENCE TABLE ###
   qiime tools import \
      --type 'FeatureData[Taxonomy]' \
      --input-format HeaderlessTSVTaxonomyFormat \
      --input-path greengenes/94_otu_taxonomy.txt \
      --output-path paired_end/greengenes_94_taxonomy.qza
```

**Next we will:**
   - Train a taxonomy classifier for our amplicon region in the reference database
      - Naive Bayes Classifier
   - We will identify our region of interestusing the primer seqeunces
      - Select only region of the total 16S that was amplified and sequenced
   - Apply the classifier to our 16S Amplicon Sequences
      - Each sequence is queried and taxonomy assigned to the closest confident level

```bash
### EXTRACT REFERENCE READS BASED ON PRIMERS AND TRIM LENGTH ###
   qiime feature-classifier extract-reads \
      --i-sequences paired_end/greengenes_94_otus.qza \
      --p-f-primer AGAGTTTGATCCTGGCTCAG \
      --p-r-primer GCTGCCTCCCGTAGGAGT \
      --p-trunc-len 320 \
      --o-reads paired_end/greengenes_94_seqs_extracted.qza

### TRAIN NAIVE BAYES CLASSIFIER FOR TAXONOMY ASSIGNMENT ###
   qiime feature-classifier fit-classifier-naive-bayes \
      --i-reference-reads paired_end/greengenes_94_seqs_extracted.qza \
      --i-reference-taxonomy paired_end/greengenes_94_taxonomy.qza \
      --o-classifier paired_end/greengenes_94_classifier.qza

### ASSIGN TAXONOMY WITH TRAINED CLASSIFIER ###
   qiime feature-classifier classify-sklearn \
      --i-classifier paired_end/greengenes_94_classifier.qza \
      --i-reads paired_end/2_0_dada2_representative_seqs.qza \
      --o-classification paired_end/3_4_assigned_greengenes_94_taxonomy.qza

```

**Finally let's visualize our taxonomic assignment**

```bash
### MAKE TAXONOMY OUTPUT VISUALIZATION ###
   qiime metadata tabulate \
      --m-input-file paired_end/3_4_assigned_greengenes_94_taxonomy.qza \
      --o-visualization paired_end/3_5_taxonomy_visualization.qzv

   qiime tools view paired_end/3_5_taxonomy_visualization.qzv
```

We did it!!!!

....but why are some confidence scores greater than 1?!? Did we break statistics? It turns out these are rounding errors and can safely be considered to be ~1 or 100% confidence. Want to know more?  Read [this](https://forum.qiime2.org/t/confidence-intervals-greater-than-1-in-custom-classifier/15014/5)


Exporting QIIME Feature Tables
----------------------------------
In order to proceed with downstream analysis in [MicrobiomeAnalyst](https://www.microbiomeanalyst.ca/), we will need to export our feature table, taxonomic assignments, and phylogenetic tree. We do this using the QIIME2 tools command.

Feature tables and taxonomy are exported in [BIOM format](https://biom-format.org/).
```bash
  qiime tools export --input-path paired_end/2_1_dada2_table.qza \
    --output-path paired_end/exported

  qiime tools export --input-path paired_end/3_4_assigned_greengenes_94_taxonomy.qza \
    --output-path paired_end/exported
```
We then need to quickly manually edit the header of the taxonomy file to match the BIOM software format. We will make a copy and then edit the copy (just in case something goes awry)
```bash
  cp paired_end/exported/taxonomy.tsv paired_end/exported/biom-taxonomy.tsv
```
Change the first line of the header in the biom-taxonomy.tsv file to read:
```bash
#OTUID  taxonomy  confidence
```
*Note: this header is case sensitive.*

Now we can add the taxonomy to the .biom file .
```bash
  biom add-metadata -i paired_end/exported/feature-table.biom -o paired_end/table-with-taxonomy.biom --observation-metadata-fp paired_end/exported/biom-taxonomy.tsv --sc-separated taxonomy
```
Finally, we need to export the phylogenetic tree for downstream phylogenetic analyses.
```bash
  qiime tools export --input-path paired_end/3_3_dada2_tree.qza \
    --output-path paired_end/rooted_tree.tre
```

We will pause here for today to take questions and meet back tomorrow at 12PM CST to take our newly created BIOM table to Microbiome Analyst. Thanks! 
=====================================

