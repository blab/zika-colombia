## Scripts for data wrangling and plotting

This repo contains jupyter notebooks for making the input dataset and plotting figures. Note that these scripts should be run inside the `colombia-python2` environment specified in `envs/colombia.python2.yaml`.

To run this environment you will need to have conda or miniconda installed. Instructions can be found [here](https://conda.io/docs/user-guide/install/macos.html?highlight=conda).

Once you have conda installed, you will need to create the environment. To do so, in a terminal run `conda env create --file <path/to/envs/colombia.python2.yaml>`.

To load the environment, run `conda activate colombia-python2`.

Once the environment is loaded, from that terminal window run `jupyter notebook`. That will ensure your notebook is using that environment.

------

`curate-dataset.ipynb` is the notebook that does data wrangling. This notebook takes a batch download from nextstrain-fauna and removes sequences that shouldn't be included in our analysis (e.g. Singapore sequences, sequences without permissions etc.)

`plot-figures.ipynb` is the notebook that plots the map with sampling locations and the epi curve.
