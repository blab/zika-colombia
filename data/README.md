### Consensus genomes

This repo contains fasta files for each of the Colombian Zika genomes that we attempted sequencing on, as well as fasta files for the full Americas phylogeographic analysis.

`publishable-zika-fauna-2018-09-06.fasta` is the input file for the full phylogeographic analysis. It contains genomes from other countries in the Americas that we have permission to use in published analyses, as well as the genomes that we generated that had 50% or more genome coverage.

`ZIKA-COL-good.fasta` contains consensus genomes that have 80% or more unambiguous bases.

`ZIKA-COL-partial.fasta` contains consensus genomes that have between 50% and 80% unambiguous bases.

`ZIKA-COL-poor.fasta` contains the consensus genomes for samples that have less than 50% unambiguous bases. Many of these consensus genomes are entirely N, and we do not use these poor quality genomes in any part of the analysis. They are included here for completeness only.

The fasta headers contain the information about the samples. For example, here's a header:

`>COL/FH16/2016|COL16|2016-06-22|colombia|valle_del_cauca|cali|minion|1d_chemistry|six_plex|stringent_porechop_demux|nanopolished|good`

The fields are separated by pipes, where all headers have this information in the same order:

1. Strain name.
2. Bedford lab identifier for the sample.
3. Sampling date, in YYYY-MM-DD format.
4. Country of sampling.
5. Department of sampling.
6. Municipality of sampling.
7. Oxford Nanopore kit chemistry that was used for library prep.
8. How many genomes were multiplexed on a single run (usually this is 6, but sometimes it can be 12).
9. How strict porechop was during demultiplexing (stringent is the strictest).
10. Whether or not the consensus genome was nanopolished to perform error correction (options are nanopolished or not_nanopolished).
11. Quality of the genome (options are good, partial, or poor).

These consensus genomes were called using [our custom pipeline](https://github.com/blab/zika-seq). More details, as well as all scripts can be found on the zika-seq repo. Briefly however consensus genomes are generated via the following process.

1. MinION signal-level data is basecalled using Albacore.
2. Reads are demultiplexed using [Porechop](https://github.com/rrwick/Porechop). _Note, to ensure that reads are potentially sorted into bins they don't belong in, we require Porechop to use two barcodes (that must match) to bin a read. This is the option that should be used, but it is not default._
3. Primers are trimmed from reads, and read depth is normalized using a custom script.
4. Reads are mapped to a reference using BWA.
5. Support for variant calls made in base-space is assessed in the signal-level data using [Nanopolish](https://github.com/jts/nanopolish).
6. Consensus genomes are called with a custom script that walks through the nanopolish output VCF file and the reference genome.
