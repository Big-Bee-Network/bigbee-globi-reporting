[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5722445.svg)](https://doi.org/10.5281/zenodo.5722445)




# Big Bee Global Biotic Interactions - reporting
Big Bee Reporting Methods for Global Biotic Interactions was copied from the [Terrestrial Parasite Tracker (methods)](https://github.com/ParasiteTracker/tpt-reporting) project

Please click on above travis badge to view current Big Bee reports. 


For archived reports from Big Bee project reports see 

## Creating a new archived report
0. Update elton to get the most recent version
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

3. run report script: generate-report.sh [datasets.tsv] 

e.g., 

```
$ ./generate-report.sh datasets.tsv
...
```

4. after generating the report, the results should be available in the ```output/``` folder. 
5. Update Zenodo publication with output files including:

`review_summary.tsv:
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
 
 datasets.zip
 All datasets reviewed for this publication.
 `
