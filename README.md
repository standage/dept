## DEPT: differential expression permutation testing

### Overview

The application of high-thoughput sequencing technologies to cDNA samples has
revolutionized the way gene expression is measured. However, despite exciting
advances in technology, algorithms, and statistical models, differential
expression analysis remains a significant challenge. Try 3 different DE analysis
packages, and chances are you'll get 3 very different lists of differentially
expressed molecules.

The purpose of this package is to encourage a healthy level of skepticism with
respect to DE analysis. A simple permutation test enables you to investigate
what proportion of your DE gene list can be attributed to noise in the DE
signal. The idea is simple: randomly shuffle condition labels for your
expression levels. If the number of DE genes reduces drastically for each label
permutation, this increases your confidence in your original results. If on the
other hand shuffling the condition labels makes little difference in the number
of DE genes reported, this is an indication that the DE signal may not be
detectable over baseline noise.

### Usage

DEPT is implemented as a simple Perl script. Type `dept -h` on the command line
for a detailed usage statement. The input to DEPT is a file containing a matrix
of expression levels (rows=genes/transcripts, columns=samples; a common format
used for DE packages). The output of DEPT is a set of new files containing the
original matrix with the columns shuffled. You can perform your permutation test
by running your DE pipeline with each of these shuffled files and comparing the
results to the original results.

The following terminal recording gives a basic demo of what `dept` is doing
under the hood.

[![asciicast](https://asciinema.org/a/5714.png)](https://asciinema.org/a/5714)
