# Genomic epidemiology supports multiple introductions and cryptic transmission of Zika virus in Colombia.


#### Allison Black*<sup>1,2</sup>, Louise H. Moncla*<sup>2</sup>, Katherine Laiton-Donato<sup>3</sup>, Lissethe Pardo<sup>3</sup>, Catalina Tovar<sup>4</sup>, Diana P. Rojas<sup>5</sup>, Ira M. Longini<sup>5</sup>, M. Elizabeth Halloran<sup>1,2</sup>, Dioselina Peláez-Carvajal<sup>3</sup>, Juan D. Ramirez<sup>4</sup>, Marcela Mercado-Reyes<sup>3</sup>, Trevor Bedford<sup>1,2</sup>.

\* These authors contributed equally to the work.

<sup>1</sup> University of Washington, Seattle, Washington, United States.
<sup>2</sup> Fred Hutchinson Cancer Research Center, Seattle, Washington, United States. <sup>3</sup> Instituto Nacional de Salud, Bogota, Colombia.
<sup>4</sup> Universidad del Rosario, Bogota, Colombia.
<sup>5</sup> University of Florida, Gainesville, Florida, United States.



## Abstract

Colombia was the second-most affected country during the American Zika virus (ZIKV) epidemic, with over 100,000 reported cases. Despite the scale of the outbreak, limited genomic sequence data were available from Colombia. We sequenced ZIKV genomes from Colombian clinical diagnostic samples and infected Aedes aegypti samples across the temporal and geographic breadth of the Colombian epidemic. Phylogeographic analysis of these genomes, along with other publicly-available ZIKV genomes from the Americas, indicates two separate introductions of ZIKV to Colombia, one of which was previously unrecognized. We estimate the timing of each introduction to Colombia, finding that ZIKV was introduced and circulated cryptically for 4 to 6 months prior to initial case detection in September 2015. These findings underscore the utility of genomic epidemiological studies for understanding epidemiologic dynamics, especially when many infections may be asymptomatic.


### Instructions for reproducing the Zika-Colombia analysis

Clone this repo by running the following command in your terminal.

`git clone https://github.com/blab/zika-colombia.git`

This analysis uses the nextstrain command line interface (CLI). Instructions for how to install and run nextstrain-cli can be found [here](https://github.com/nextstrain/cli).

After installing nextstrain-cli, change back to your `zika-colombia` directory.

Run the analysis with `nextstrain build .`

Then, visualize the analysis with `nextstrain view auspice`

If you want to customize your analysis, you can do so by editing the Snakefile. The cli provides a dockerized wrapper for Nextstrain Augur and Nextstrain Auspice, so any commands that you could normally give to augur or auspice can be integrated into the Snakefile by editing shell commands and adding params. File extenstions and locations can also be edited by changing paths in the Snakefile.

If you are wondering what commands you can give the different augur executables, you can look at augur help statements. To do so, run `nextstrain shell` to bring up the augur environment. Then explore with `augur --help` or `augur <program> --help`.
