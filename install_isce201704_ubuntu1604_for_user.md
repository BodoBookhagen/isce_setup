### Setup ISCE on an installed system (bash)
```
cd ~
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```
Use default installation location and I suggest to add Miniconda3 install location to PATH variable. You may to rerun ~/.bashrc or logout/login to get net path settings

```
source ~/.bashrc
```

### Install environment for ISCE
Use isce_processing/isce_201704.yml for setting up conda

Note that isce_201704.yml is a modified version from David Bekaert's github site https://github.com/dbekaert in directory isce_notes/Ubuntu/isce_201609.yml
```
cd ~
conda env create -f isce_setup/isce_201704.yml
```

# Setup ISCE environment:
```
cd ~
mkdir .isce
```

Copy isceenv_20170403 to ~/.isce/.isceenv_20170403 (*NOTE* the '.')
```
cp isce_processing/isceenv_20170403 ~/.isce/.isceenv_20170403
```

### Add aliases to ~/.bashrc
```
alias start_isce="source activate isce_201704; source ~/.isce/.isceenv_20170403"
```

### Start and test ISCE environment with:
```
start_isce
insarApp.py --help --steps
topsApp.py --help
```
