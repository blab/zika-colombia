## Supplemental Analysis

We thought it would be interesting to see where genomes with less than 50% genome coverage cluster within the tree. This supplemental analysis completely mirrors the full analysis for the manuscript, albeit with the addition of 4 sequences that had between 4% and 35% genomic coverage. Topology should not be trusted for sequences that lack that much data, but it is an interesting exploratory analysis, especially from the standpoint of investigating how reasonably trees look with varying data quality.

The input fasta for the supplemental analysis is different from the full analysis, and some changes have been made to the output file naming (all documented in the Snakefile in this supplemental repo).

To run the Supplemental analysis, `cd` into the `supplemental-analysis` repo. Then run `nextstrain build .` and to visualize run `nextstrain view auspice`. Because all the necessary directories are mirrored into the supplemental-analysis directory, the analysis should run as long as it is called from this directory specifically.
