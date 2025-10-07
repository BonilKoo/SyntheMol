# Generating molecules with REINVENT 4

Below are instructions for generating molecules with REINVENT 4, a generative flow-based model.


## Installation

Clone the forked repository.

```bash
git clone https://github.com/swansonk14/REINVENT4
cd REINVENT4
git checkout antibiotics
```

Install dependencies.

```bash
conda create -y -n reinvent4 python=3.10
conda activate reinvent4
pip install pandas==2.1.2
pip install chemprop==1.6.1
pip install descriptastorus==2.6.1
pip install typed-argument-parser==1.9.0
python install.py cu124
```

**Note:** If you get the issue `ImportError: libXrender.so.1: cannot open shared object file: No such file or directory`, run `conda install -c conda-forge xorg-libxrender`.

## Download prior

Download the reinvent prior.

```bash
wget https://zenodo.org/records/15641297/files/reinvent.prior
mv reinvent.prior priors
```

## Generate molecules

```bash
mkdir -p runs/antibiotics
cd runs/antibiotics
reinvent -l antibiotics.log ../../configs/antibiotics.toml
```
