[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5722445.svg)](https://doi.org/10.5281/zenodo.5722445)




# Big Bee Global Biotic Interactions - reporting
Big Bee Reporting Methods for Global Biotic Interactions was copied from the [Terrestrial Parasite Tracker (methods)](https://github.com/ParasiteTracker/tpt-reporting) project

Please click on above travis badge to view current Big Bee reports. 


For archived reports from Big Bee project reports see 

## Creating a new archived report
0. Update elton to get the most recent version

[update to new version of generate-report.sh?]

1. Make a list of GloBI/Elton index configurations species interaction datasets. (e.g., see https://raw.githubusercontent.com/globalbioticinteractions/globalbioticinteractions.github.io/master/_data/bigbee.tsv)

Example:
```
cat ~/proj/globi/globalbioticinteractions.github.io/_data/bigbee.tsv\
| tail -n+2\
| cut -f10\
| sort\
| uniq
```

yields:

```
globalbioticinteractions/ummz-ummzi
globalbioticinteractions/asu-asuhic
globalbioticinteractions/cas-ent
globalbioticinteractions/emec
globalbioticinteractions/fsca
globalbioticinteractions/ku-semc
globalbioticinteractions/lacm-lacmec
globalbioticinteractions/mcz
globalbioticinteractions/sdnhm-sdmc
globalbioticinteractions/ucm-ucmc
globalbioticinteractions/ucsb-izc
globalbioticinteractions/unhc-unhc
```

2. Save the list to a file (e.g., datasets.tsv)

3. Run report script: generate-report.sh [datasets.tsv] 

e.g., 

```
$ ./generate-report.sh datasets.tsv
...
```


4. After generating the report, the results should be available in the ```output/``` folder. 

5. Run Globi_bee_data.sh to generate report of just bee interactions by collection

6. Create a new Zenodo verson. Copy the files over to the new version and update the text. Include the summary statistics for Bee Library in the text and in an associated PDF file.

7. copy-paste the zenodo description into the README file. Currently, only the auto-generated README is present, and your manual edits are valuable additions, providing context to the data without having to look at Zenodo's metadata.

8. suggest to publish the metrics currently captured pdf as separate tables in csv/tsv format

```
review_summary.tsv:
  Summary across all reviewed collections of the total number of distinct review comments.

review_summary_by_collection.tsv:
  Summary by the reviewed collection of the total number of distinct review comments.

indexed_interactions_by_collection.tsv: 
  Summary of the number of indexed interaction records by institutionCode and collectionCode.

review_comments.tsv.gz:
  All review comments by collection.

indexed_interactions_full.tsv.gz:
  All indexed interactions for all reviewed collections.

indexed_interactions_simple.tsv.gz:
  All indexed interactions for all reviewed collections selecting only sourceInstitutionCode, sourceCollectionCode, sourceCatalogNumber, sourceTaxonName, interactionTypeName and targetTaxonName.

datasets_under_review.tsv:
  Details on the datasets under review.

elton.jar: 
  Program used to update datasets and generate the review reports and associated indexed interactions.
  
Big Bee Metrics from the Bee Library and GloBI - July 27 2022.pdf:
 Summary statistics from the Bee Library and GloBI about data partners

indexed_interactions_bees.tsv:
 All indexed bee interactions
 
datasets.zip:
 All datasets reviewed for this publication
 ```
