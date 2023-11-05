Part1- Bugs

The bug I chose is the method ```reversed```

A failure induced input is:
```
int[] input2 = { 6,4,7,6};
assertArrayEquals(new int[]{6,7,4,6}, ArrayExamples.reversed(input2));
```
An input that does not induce failure is:
```
int[] input1 = { };
assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
```
Symptom:
![image](lab4.png)

Before code change:
```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

After code change:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

The fix addresses the issue because for the original code, the code changed elements on the index of the input array to the elements on the reversed index of the newly established array, which has empty elements in all indexes. By changing the code and making the element on index of newly established array change to elements on the reversed index of the input array, and return the new array, we can achieve the intended goal of the code.

Part 2.
I choose ```grep``` and the first command-line option is ```-c```.

1st example:
```
$ grep -c "base pairs"  technical/plos/journal.pbio.0020190.txt
2
```
2nd example:
```
$ grep -c "base pairs"  technical/plos/pmed.0020203.txt
0
```

command-option ```grep -c``` counts number of lines that contain the input string in a file. It's useful since sometimes we don't need to know the specific lines in a file that contain certain strings and we just want to know how many lines are there that contain such string, the ```-c``` will give us this useful information with simpler output in terminal compared to ```grep``` without ```-c```.

The second command-line option is ```-v```.

1st example:
```
$ grep -v "a" technical/plos/pmed.0020203.txt






        in
        (www.plosbiology.org).
        published in



```

2nd example:
```
$ grep -v "the" technical/plos/journal.pbio.0020190.txt





        this same sense, we can envision that all DNA strands are alike because all are monotonous
        considering its basic function of inheritance, in which all parts of all chromosomes must
        inheritance is fundamentally a consequence of DNA's general molecular structure, and not of
        well appreciated. Muller did not know that genes are made of DNA, but he did realize that,
        So where does recombination (Box 1) fit in? Is recombination something that happens to
        joining of a variable gene segment and a joining segment to form an immunoglobulin gene
        chromosomes have local recombination hotspots where crossing over is much more likely to
        are flanked by “coldspots,” regions of lower than average frequency of recombination
        (Lichten and Goldman 1995).


        of Human Disease Alleles
        Recombination hotspots are of strong interest to at least two quite different groups of
        1989; Sun et al. 1989; Keeney et al. 1997; Lopes et al. 1999; Allers and Lichten 2001;
        Hunter 2003).
        individual nucleotide positions—single nucleotide polymorphisms (SNPs). Each particular
        could search for genes with disease alleles by looking for a pattern of SNPs that is found
        called “association mapping,” and it is basically a search for linkage disequilibrium
        often fairly long regions with very high linkage disequilibrium (Daly et al. 2001; Patil et
        al. 2001; Gabriel et al. 2002). This pattern of variation has been characterized as
        occurring in “haplotype blocks,” which are apparent regions of low recombination (or high
        eight haplotypes for a series of SNPs found over a region of a chromosome. Given diverse
        blocks (Wang et al. 2002; Innan et al. 2003; Phillips et al. 2003; Stumpf and Goldstein

      
        The Evolution of Recombination and (Possibly) Recombination Hotspots
        been put forward to explain why it would be evolutionarily advantageous for genes to
        et al. 2001; Kong et al. 2002).
        mutations that raise recombination rates would be favored by natural selection (Barton
        1995; Otto and Barton 1997; Otto and Barton 2001; Otto and Lenormand 2002). The basic idea
        is that linkage disequilibrium can easily occur (for many reasons) between two (or more)
        more efficiently. If an allele that is under positive or negative selection always occurs
        second locus. As new, multilocus configurations of beneficial alleles are generated (by
        directional selection, like that which occurs in artificial selection experiments, which
        often generates a correlated elevation in recombination rates (Otto and Lenormand
        2002).
        were under selection. This situation would create a kind of selection pressure favoring
        recombinant haplotypes and thus also favoring those chromosomes that happen to have a high
        recombination rates (i.e., hotspots and coldspots for recombination) to fluctuate in
        location and intensity, in ways that would be hard to precisely predict without knowing
        have been.
        PLoS Biology is especially interesting. They report that chimpanzees do
        characterized recombination hotspot (Jeffreys and Neumann 2002). Ptak et al.'s is a
        contrast in linkage patterns between humans and our closest relatives suggests that
        recombination hotspots can evolve fairly quickly.


        Functional Constraints on Recombination Hotspots
        disequilibrium. Particularly important in this regard is that some wellstudied organisms
        Drosophila melanogaster ) have not shown evidence of
        hotspots.
        segregation of chromosomes during meiosis (Paques and Haber 1999; Lichten 2001; Hunter
        D. melanogaster or
        C. elegans (Zickler and Kleckner 1999; MacQueen et al. 2002;
        McKim et al. 2002; Hunter 2003; Page and Hawley 2003). Double-strand breaks and
        Recombination during meiosis seems to be required for proper chromosome segregation;
        however, in those organisms where recombination and double-strand-break hotspots occur,
        recombination machinery has been partly co-opted for chromosome alignment in some
        existence of recombination hotspots.


        Conclusions
        Recombination hotspots co-occur with double-strand-break hotspots in some eukaryotes,
        linkage disequilibrium (haplotype blocks) and thus on our ability to map disease alleles by





```

The command ```grep -v``` prints lines that do not contain the input string in the terminal. It's useful when we don't want to look for lines that contain certain strings but lines that do not contain the strings in a file.

The third command-line option is "-n":

1st example：
```
$ grep -n "base pairs"  technical/plos/journal.pbio.0020190.txt
22:        sequence, which is a specific series of eight base pairs in the DNA of the bacterial
31:        chromosomes, on the order of one or two thousand base pairs of DNA (or less—their length is
```

2nd example:
```
$ grep -n "base pairs"  technical/biomed/rr196.txt
200:          approximately 500 base pairs upstream of the stop codon,
```

The command ```grep -n``` not only prints out the line that contains the input string but also shows the line number of that line in a file. It's useful when we want to know the exact position of the line that contains the string in a file.

The forth command-line option is ```-w```

1st example:
```
$ grep -w "a"  technical/biomed/rr196.txt
        fiber shortening with a corresponding shift in the
        of emphysematous hamsters, an increase in IIa fibers and a
        than hamster, and with the availability of a
        elastase-induced emphysema as a model in which the
          emphysema induction by a single intratracheal
          volume of saline without a mortality.
          Each strip was mounted horizontally in a bath of
          1°C. One end of the strip was tied to a fixed post with
          tendon at the other end was fixed to the arm of a
          a movable platform with a single tie. Platinum electrodes
          strip on either side. The muscles were stimulated with a
          developed in our laboratory. A Pentium computer with a
          cannulated with a 16 g intravenous catheter (Angiocath;
          established, and the lung was inflated to a distending
          at a wavelength of 260 nm. mRNA (150 ng) was reverse
          single 5' oligonucleotide common primer, designed from a
          oligonucleotide primer, designed from a divergent portion
          target sequences. However, this control template yields a
          The PCR was performed in a 50 μl total reaction
          performed in a thermal cycler with an initial denaturing
          60°C, 50 seconds at 70°C, and a final step of 3 minutes
          amplified signal was on the linear portion of a
          semilogarithmic plot of the yield expressed as a function
          total sample was then calculated from the fraction of a
          MHC mRNA isoforms in a given sample [ 19 ] . We performed
          with a rabbit anti-rat laminin primary antibody (Sigma,
          St Louis, Missouri) at a dilution of 1:2500, followed by
          a fluorescein-conjugated sheep anti-rabbit IgG secondary
          antibodies were used. For BF-F3 we used a primary
          antibody dilution of 1:50, an 18 hour incubation, and a
          antibody. For BF-35 we used a primary antibody dilution
          of 1:10, a 24 hour incubation, and a goat anti-mouse IgG
          Data are reported as means ± SE. We used a
          repeated-measures analysis of variance with a Huynh-Feldt
          We noted a group-by-type interaction and then performed 
          was a significant decrease in the expression of MHC IIb
          isoform, all demonstrated a trend to greater expression
          had a significantly lower percentage of fibers classified
          as IIb and a trend toward increased numbers of IIx and
          Figure 2shows a typical panel from serial sections of one
          strongly correlated with a shift to slower MHC isoforms
          with a
          emphysematous diaphragm was less fatiguable with a
        ] : that is, they too are manifested as a shift toward
        recently could a change in fiber type distribution be
        hamster diaphragm has demonstrated a change in twitch
        Intratracheal instillation of elastase in rats creates a
        results in relation to Kanbara's would be that there was a
        3 7 ] . Only in one recent paper was a shift in MHC in
        We demonstrate here a shift from IIb toward IIx in
        levels. Although this shift toward a slower isoform is not
        adaptations have a chance to occur, the greater compliance
        been suggested by others, at least in part a function of
        MHC isoforms [ 29 38 ] . Although one paper has shown a
        fibers [ 38 ] , and another has shown only a significant
        decrease in type IIb fibers [ 39 ] , a third paper reported
        a surprising increase in type IIb fibers [ 40 ] .
        a pure increase in the workload on the muscle.
        In addition to being the first demonstration of a
        demonstrate that such a shift toward slower isoforms in
        emphysema has a significant physiologic impact on
        a shift only between the fast isoforms but away from IIb
        whole muscles, a slower maximum velocity of shortening in
        et al. [ 48 ] have shown a major
        responsible for a significant fraction of energy
        In sum, we have demonstrated a significant decrease in
        in vitro , including a longer time to
        peak tension and a greater resistance to fatigue in
```

2nd example:
```
$ grep -w "an"  technical/plos/pmed.0020203.txt
        studies are an important part of medical research, but which ones, if any, belong in a
```

The command-line option ```grep -w``` prints out lines that specifically contain the input word and avoid viewing the input as a string that can be the substring of another word. For example ```grep -w "a"``` will only prints lines that contain the word "a", but ```grep "a"``` will prints lines that not only contain the word "a" but also lines that contain words that have "a" in them. It's useful when we want to look for lines in a file that specifically contain a word and do not want to include words that are not identical to the target word but the target word is a substring of those words.
