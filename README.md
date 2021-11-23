[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5722445.svg)](https://doi.org/10.5281/zenodo.5722445)




# Big Bee Global Biotic Interactions - reporting
Big Bee Reporting Methods for Global Biotic Interactions was copied from the Terrestrial Parasite Tracker (methods)[https://github.com/ParasiteTracker/tpt-reporting] project

Please click on above travis badge to view current Big Bee reports. 


For archived reports from Big Bee project reports see 

## Creating a new archived report
0. Update elton to get the most recent version
1. Make a list of GloBI/Elton index configurations species interaction datasets. (e.g., see https://raw.githubusercontent.com/globalbioticinteractions/globalbioticinteractions.github.io/master/_data/bigbee.tsv)

Example:
```
$ cat ~/proj/globi/globalbioticinteractions.github.io/_data/bigbee.tsv | tail -n+2 | cut -f10 | sort | uniq
EMTuckerLabUMMZ/ummzi
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
