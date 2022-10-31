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

### LESS

less -N: This option tells the less command to display line numbers along with the file.
```
Arjun Suresh Kumar@ARJUN-M15 MINGW64 ~/Documents/Programming/FA22/skill-demo1/technical/plos (main)
$ less -N pmed.0010028.txt
    1
      2
      3
      4
      5         Introduction
      6         The immunotherapy of cancer holds promise in harnessing the host immune response to
      7         specifically target tumor cells without harming normal tissues. Strategies involve adoptive
      8         cellular therapy or active immune induction (commonly referred to as “cancer vaccination”).
      9         Cancer vaccines may consist of whole tumor cells or tumor lysates, but identification of
     10         tumor-associated antigens (TAAs) over the past decade has made possible the use of specific
     11         proteins or peptides as cancer vaccines. The anti-tumor potential of TAA-specific CD8+ T
     12         cells has been illustrated by the demonstrated capacity of adoptive T cell therapy to
     13         reduce tumor size [1]. While endogenous anti-tumor CD8+ T cell responses may already exist
     14         in some cancer patients [2], vaccination with TAA-derived peptides, and in particular
     15         heteroclitic peptide analogs, increases the frequency of TAA-specific T cell responses to
     16         detectable levels in many patients [3,4,5,6,7,8,9]. Heteroclitic peptide analogs are
     17         created by substitutions at anchor residues resulting in increased association of peptide
     18         with the major histocompatibility complex (MHC) [10]. Consequently, heteroclitic peptide
     19         analogs are predicted to be more immunogenic than their native counterparts because of more
     20         stable binding at the surface of antigen-presenting cells (APCs). Indeed, T cells capable
     21         of tumor lysis have been isolated from patients vaccinated with heteroclitic peptide
     22         [8,11,12,13]. However, the presence of TAA-specific T cells elicited by vaccination often
     23         does not correlate with clinical responses [3,14,15,16,17].
     24         Various reasons for the paradoxical coexistence of cancer cells and TAA-specific T cells
     25         within patients have been proposed [18,19]. One possibility is that elicited TAA-specific T
     26         cells are not optimally functional in vivo [2,18]. Another possibility is that T cells
pmed.0010028.txt
```

less --pattern: This command-line option tells the less command to begin displaying the file at the given string. This would be useful in cases where the user only needs information relevant in one part of the document.
```
Arjun Suresh Kumar@ARJUN-M15 MINGW64 ~/Documents/Programming/FA22/skill-demo1/technical/plos (main)
$ less --pattern="binding" pmed.0010028.txt
stable binding at the surface of antigen-presenting cells (APCs). Indeed, T cells capable
        of tumor lysis have been isolated from patients vaccinated with heteroclitic peptide
        [8,11,12,13]. However, the presence of TAA-specific T cells elicited by vaccination often
        does not correlate with clinical responses [3,14,15,16,17].
        Various reasons for the paradoxical coexistence of cancer cells and TAA-specific T cells
        within patients have been proposed [18,19]. One possibility is that elicited TAA-specific T
        cells are not optimally functional in vivo [2,18]. Another possibility is that T cells
        inefficient in tumor recognition or lysis are induced by vaccination [20]. It is becoming
        recognized that antigen-specific T cells may have substantially different requirements for
        cognate peptide (the peptide that is recognizable to a specific T cell clone) for efficient
        target lysis [20,21,22,23]. “Recognition efficiency” (RE) (also known as “functional
        avidity”) is a measure of the sensitivity of a T cell to different peptide concentrations
        for stimulation [24,25,26]. We hypothesized that high antigen densities on APCs resulting
        from vaccination with heteroclitic peptide may paradoxically drive T cells of predominantly
        low RE, which are not efficiently activated by the endogenous expression levels of native
        peptides on tumor cells. Consequently, such T cells would be ineffective in tumor cell
        destruction. Support for this notion is emerging: T cells with low RE are predominantly
        expanded in vitro with high peptide concentration [22]. Moreover, in vitro stimulation of T
        cells from healthy donors with heteroclitic peptides results in expansion of cells with a
        wide range of RE [23]. A similar phenomenon may occur in vivo, leading to TAA-specific T
        cells of low RE depending on the nature of antigen stimulation [20].
        While isolated T cell clones with low RE have indeed been generated from melanoma
        patients following heteroclitic peptide vaccination, the proportion of vaccine-elicited T
        cell responses these cells represent in vivo is not clear. If predominantly high-RE,
        tumor-cytolytic T cells are generated, then a small fraction of low-RE T cells generated
        would be of little consequence. However, if predominantly low-RE T cells are generated,
pmed.0010028.txt
```

less --chop-long-lines: This command tells the less command to not display the off-screen portion of long lines as wrapped-around. This might be usueful in files with irrelevant but very long lines interrupting the important information in between.
```
Arjun Suresh Kumar@ARJUN-M15 MINGW64 ~/Documents/Programming/FA22/skill-demo1/technical/plos (main)
$ less --chop-long-lines pmed.0010028.txt
Introduction
        The immunotherapy of cancer holds promise in harnessing the host immune response to
        specifically target tumor cells without harming normal tissues. Strategies involve adoptive
        cellular therapy or active immune induction (commonly referred to as “cancer vaccination”).
        Cancer vaccines may consist of whole tumor cells or tumor lysates, but identification of
        tumor-associated antigens (TAAs) over the past decade has made possible the use of specific
        proteins or peptides as cancer vaccines. The anti-tumor potential of TAA-specific CD8+ T
        cells has been illustrated by the demonstrated capacity of adoptive T cell therapy to
        reduce tumor size [1]. While endogenous anti-tumor CD8+ T cell responses may already exist
        in some cancer patients [2], vaccination with TAA-derived peptides, and in particular
        heteroclitic peptide analogs, increases the frequency of TAA-specific T cell responses to
        detectable levels in many patients [3,4,5,6,7,8,9]. Heteroclitic peptide analogs are
        created by substitutions at anchor residues resulting in increased association of peptide
        with the major histocompatibility complex (MHC) [10]. Consequently, heteroclitic peptide
        analogs are predicted to be more immunogenic than their native counterparts because of more
        stable binding at the surface of antigen-presenting cells (APCs). Indeed, T cells capable
        of tumor lysis have been isolated from patients vaccinated with heteroclitic peptide
        [8,11,12,13]. However, the presence of TAA-specific T cells elicited by vaccination often
        does not correlate with clinical responses [3,14,15,16,17].
        Various reasons for the paradoxical coexistence of cancer cells and TAA-specific T cells
        within patients have been proposed [18,19]. One possibility is that elicited TAA-specific T
        cells are not optimally functional in vivo [2,18]. Another possibility is that T cells
pmed.0010028.txt
```

### FIND

find -mindepth: This command line option tells the find command to begin looking for matches a certain number of subdirectories into the file structure. This would be useful in cases where there are files higher up in the tree that need to be avoided.
```
Arjun Suresh Kumar@ARJUN-M15 MINGW64 ~/Documents/Programming/FA22/skill-demo1/technical (main)
$ find 911* -mindepth 1
911report/chapter-1.txt
911report/chapter-10.txt
911report/chapter-11.txt
911report/chapter-12.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-2.txt
911report/chapter-3.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-8.txt
911report/chapter-9.txt
911report/preface.txt
```

find -maxdepth: This command line option tells the find command to begin looking for matches within certain number of subdirectories into the file structure. This would be useful in cases where there are files lower down in the tree that need to be avoided.
```
Arjun Suresh Kumar@ARJUN-M15 MINGW64 ~/Documents/Programming/FA22/skill-demo1/technical (main)
$ find 911* -maxdepth 0
911report
```