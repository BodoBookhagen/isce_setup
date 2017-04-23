### setup GIAnT on an installed system
cd
conda config --add channels https://conda.anaconda.org/conda-forge

### Install environment for GIAnT
#giant.yml is a modified version from David Bekaert's github site https://github.com/dbekaert in directory isce_notes/Ubuntu/giant.yml

conda env create -f isce_processing/giant.yml

### Setup file ~/.isce/.giantenv
#edit giantenv to match your local giant installation, e.g., edit GIANT_DIR
cp isce_processing/giantenv .isce/.giantenv

#add alias to ~/.bashrc
alias start_giant="source ~/.isce/.giantenv; source activate giant"

start_giant
cd $GIANT_DIR
python2 setup.py build_ext


