# Lab Report 4

## Week 5 - Command-Line Options

### GREP

grep -r: This option searches through files recursively throughout subdirectories, which would be used in cases where an entire folder must be searched, rather than specifying the name of each subfolder.
```
Arjun Suresh Kumar@ARJUN-M15 MINGW64 ~/Documents/Programming/FA22/skill-demo1/technical (main)
$ grep -r "2024"
biomed/cc350.txt:        (Pulsiocath 2024 L, Pulsion, Munich, Germany) and 24 h
government/Gen_Account_Office/d01591sp.txt:begins to decline. By 2024, gross national saving as a share of GDP
```

grep -i: This option tells the grep command to ignore upper and lower cases. This would be useful when only the topic of the search is important, not an exact character match.
```
Arjun Suresh Kumar@ARJUN-M15 MINGW64 ~/Documents/Programming/FA22/skill-demo1/technical (main)
$ grep -i "semi-public" */*.txt
plos/pmed.0010046.txt:        semi-public database maintained by the United States Food and Drug Administration, and
plos/pmed.0010060.txt:        A Semi-Public Database
```

grep -n: This option tells the grep command to print out the exact line within the file where the given string was found. This would be useful in a case where the user needed to view the surrounding context of the string in the document.
```
Arjun Suresh Kumar@ARJUN-M15 MINGW64 ~/Documents/Programming/FA22/skill-demo1/technical (main)
$ grep -n "semi-public" */*.txt
plos/pmed.0010046.txt:60:        semi-public database maintained by the United States Food and Drug Administration, and
```
