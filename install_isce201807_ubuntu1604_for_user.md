# Setup ISCE on a Ubuntu system with ISCE installed (bash)
In a multi-user environment, ISCE may already be installed and setup. These steps describe how to make these available to other users on that system.
```
cd ~
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```
Use default installation location and I suggest to add Miniconda3 install location to PATH variable. You may to rerun ~/.bashrc or logout/login to get net path settings:

```
source ~/.bashrc
```

## Install environment for ISCE 2.2.0
Make sure that conda is part of your path (if you didn't run `source ~/.bashrc` then `run 'export PATH=/home/bodo/miniconda3/bin:$PATH'`).

Use isce_processing/isce_201708.yml for setting up conda. Note that isce_201708.yml is a modified version from David Bekaert's github site https://github.com/dbekaert in directory isce_notes/Ubuntu/isce_201609.yml. Clone this repository and create a conda environment:
```
cd ~
git clone https://github.com/BodoBookhagen/isce_setup.git
conda env create -f isce_setup/isce_201807.yml
```


## Setup ISCE environment:
```
cd ~
mkdir .isce
```

Copy isceenv_201807 to ~/.isce/.isceenv_201807 (*NOTE* the '.') and edit the directory containing ISCE (if necessary):
```
cp isce_setup/isceenv_201807 ~/.isce/.isceenv_201807
```


## Add aliases to ~/.bashrc
Edit .bashrc and add this line to allow easy start.
```
alias start_isce="source activate isce_201807; source ~/.isce/.isceenv_201807"
```


## Start and test ISCE environment with:
At first run, you may have to install pulp if you want to use the 2stage solver.

```
start_isce
conda install opencv
pip install pulp 
insarApp.py --help --steps
topsApp.py --help
```
