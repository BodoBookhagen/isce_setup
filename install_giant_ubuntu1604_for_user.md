# Setup GIAnT on an installed system

## Install Conda and dependencies for GIAnT
Note that giant.yml is a modified version from David Bekaert's github site https://github.com/dbekaert in directory isce_notes/Ubuntu/giant.yml.

```
cd ~
conda config --add channels https://conda.anaconda.org/conda-forge
conda env create -f isce_processing/giant.yml
```

## Setup GIAnT environment ~/.isce/.giantenv
Edit giantenv to match your local giant installation, e.g., edit GIANT_DIR
```
cd ~
cp isce_processing/giantenv .isce/.giantenv
```

## Add alias to ~/.bashrc
```
alias start_giant="source ~/.isce/.giantenv; source activate giant"
```

Start environment for GIAnT processing with
```
start_giant
```


