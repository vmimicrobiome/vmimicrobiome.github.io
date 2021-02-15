
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
