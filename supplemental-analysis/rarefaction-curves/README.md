# Relationships between number of samples and number of introductions detected.

For one of our supplemental analyses we wanted to show how the number of introductions observed in the tree varied depending on the number of viruses sampled from a specific country. We performed this analysis for viruses from Mexico (which is well sampled) as a comparator to this relationship for Colombia.

### Running the supplemental analysis

Given our desire to look at numbers of introductions over varying numbers of samples (with multiple trials per number of sequences) I have _a lot_ of input data files. All the input files for this supplemental analysis were generated using [this script](https://github.com/blab/zika-colombia/blob/master/scripts/curate-dataset.ipynb).

I've made Snakefiles to reproducibly run a workflow to do all of the Colombian analysis and all of the Mexican analysis, and these can be found in the `colombia` and `mexico` directories respectively.

In addition, since there are so many jobs for these analyses I'm running these nextstrain builds on AWS. For example, there is an analysis for sampling only 1 sequence from Mexico, 2 sequences from Mexico, 3 sequences etc. all the way up to 50 sequences from Mexico, and for each of these subsampled amounts there are 5 separate trials. Thus this analysis has 5 x 50 = 250 jobs. Estimating that each build takes ~15 minutes, I have 15 x 250 = 62.5 hours of work. So in order to have everything finish in about an hour, I want to have around 60 CPUs, with a CPU for each job. With AWS I can get a machine with 36 or 72 CPUs, so I'll set this up to run on the 72.

For running the Mexican analysis the command (from within the `mexico` directory) is:

`nextstrain build --aws-batch --aws-batch-cpus 72 --aws-batch-memory 129600 . --jobs 72`

where cpus and jobs are set to 72 to max out a specific machine offering that AWS has, and memory is 72 x 1800 = 129600.

The Colombian analysis has fewer sequences, and therefore makes use of the 36 CPU instance.
