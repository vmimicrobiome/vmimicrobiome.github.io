
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
### Practice time!
We want you to be comfortable analyzing your data (or data a collaborator sent you) in MicrobiomeAnalyst at the end of this workshop. So! We are going to break into groups and you will go through the MicrobiomeAnalyst workflow together with the Atacama Soils dataset. This dataset can be found in the practice_dataset folder. We borrowed this dataset from [a classic QIIME tutorial](https://docs.qiime2.org/2020.11/tutorials/atacama-soils/).

**MicrobiomeAnalyst tasks**
1. Upload the data, using the BIOM format option. A couple of quick notes: 1) This dataset's taxonomy is in QIIME format (like the American Gut dataset earlier); 2) You might get an error about sample names not matching in the OTU table and metadata. You can ignore this error (most of the sample names do match, which is good enough for our purposes today).
2. Filter low prevalence and variance features. Note: you may want to use the mean abundance value filter for this very small and sparse dataset.
3. Rarefy and scale data.
4. Look at taxonomic differences (Visual exploration).
5. Investigate differences in alpha and beta diversity (Community profiling).
6. Test some hypotheses (Clustering & correlation/Comparison & classification).

**Questions to discuss**
1. How do different count and variance filters influence how many features are retained?
2. Can you visually identify any taxonomic differences between transects or based on other metadata categories?
3. How does vegetation presence (or other metadata categories) affect alpha and beta diversity of the soil microbes?
4. Are any features differentially abundant based on any metadata categories? Do the different methods agree?
