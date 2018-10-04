### Consensus genomes

This repo contains fasta files for each of the Colombian Zika genomes that we attempted sequencing on, as well as fasta files for the full Americas phylogeographic analysis.

`publishable-zika-fauna-2018-09-06.fasta` is the input file for the full phylogeographic analysis. It contains genomes from other countries in the Americas that we have permission to use in published analyses, as well as the genomes that we generated that had 50% or more genome coverage.

`ZIKA-COL-good.fasta` contains consensus genomes that have 80% or more unambiguous bases.

`ZIKA-COL-partial.fasta` contains consensus genomes that have between 50% and 80% unambiguous bases.

`ZIKA-COL-poor.fasta` contains the consensus genomes for samples that have less than 50% unambiguous bases. Many of these consensus genomes are entirely N, and we do not use these poor quality genomes in any part of the analysis. They are included here for completeness only.

These consensus genomes were called using [our custom pipeline](https://github.com/blab/zika-seq). More details, as well as all scripts can be found on the zika-seq repo. Briefly however consensus genomes are generated via the following process.

1. MinION signal-level data is basecalled using Albacore.
2. Reads are demultiplexed using [Porechop](https://github.com/rrwick/Porechop). _Note, to ensure that reads are potentially sorted into bins they don't belong in, we require Porechop to use two barcodes (that must match) to bin a read. This is the option that should be used, but it is not default._
3. Primers are trimmed from reads, and read depth is normalized using a custom script.
4. Reads are mapped to a reference using BWA.
5. Support for variant calls made in base-space is assessed in the signal-level data using [Nanopolish](https://github.com/jts/nanopolish).
6. Consensus genomes are called with a custom script that walks through the nanopolish output VCF file and the reference genome.
