[![Build Status](https://travis-ci.org/ParasiteTracker/tpt-reporting.svg?branch=master)](https://travis-ci.org/ParasiteTracker/tpt-reporting) [![DOI]()]() 



# Big Bee Global Biotic Interactions -reporting
Big Bee Reporting Methods for Global Biotic Interactions was copied from the Terrestrial Parasite Tracker methods project

Please click on above travis badge to view current Big Bee reports. 


For archived reports from TPT project see https://doi.org/10.5281/zenodo.3685364 and https://globalbioticinteractions.org/parasitetracker

## Creating a new archived report
1. Make a list of GloBI/Elton index configurations species interaction datasets. (e.g., see https://raw.githubusercontent.com/globalbioticinteractions/globalbioticinteractions.github.io/master/_data/parasitetracker.tsv)

Example:
```
$ curl -Ls "https://raw.githubusercontent.com/globalbioticinteractions/globalbioticinteractions.github.io/master/_data/parasitetracker.tsv" | tail -n+2 | cut -f10 | sort | uniq | head -n5
EMTuckerLabUMMZ/ummzi
globalbioticinteractions/ansp-para
globalbioticinteractions/bpbm-ent
globalbioticinteractions/brtc-para
globalbioticinteractions/byu-byuc
```

Another example of a list related to [Big Bee TCN](https://big-bee.net):

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

2. Save the list to a file (e.g., somefile.tsv)

3. run report script: generate-report.sh [filename] 

e.g., 

```
$ ./generate-report.sh somefile.tsv
...
```

4. after generating the report, the results should be available in the ```output/``` folder. 
