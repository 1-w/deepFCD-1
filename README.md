<h1 align="center">
  <b>Multicenter Validated Detection of Focal Cortical Dysplasia using Deep Learning</b><br>
</h1>

<p align="center">
      <a href="https://www.python.org/">
        <img src="https://img.shields.io/badge/Python-3.7-ff69b4.svg" /></a>
      <a href= "https://keras.io/">
        <img src="https://img.shields.io/badge/Keras-2.2.4-2BAF2B.svg" /></a>
      <a href= "https://github.com/Theano/Theano">
        <img src="https://img.shields.io/badge/Theano-1.0.4-2BAF2B.svg" /></a>
      <a href= "https://github.com/NOEL-MNI/deepFCD/blob/main/LICENSE">
        <img src="https://img.shields.io/badge/License-BSD%203--Clause-blue.svg" /></a>
      <a href="https://doi.org/10.5281/zenodo.4521706">
        <img src="https://zenodo.org/badge/DOI/10.5281/zenodo.4521706.svg" alt="DOI"></a>
</p>


------------------------

![](assets/diagram.jpg)

### Please cite:
```TeX
@article{GillFCD2021,
  title = {Multicenter Validated Detection of Focal Cortical Dysplasia using Deep Learning},
  author = {Gill, Ravnoor Singh and Lee, Hyo-Min and Caldairou, Benoit and Hong, Seok-Jun and Barba, Carmen and Deleo, Francesco and D'Incerti, Ludovico and Coelho, Vanessa Cristina Mendes and Lenge, Matteo and Semmelroch, Mira and others},
  journal = {Neurology},
  year = {2021},
  publisher = {Americal Academy of Neurology},
  code = {\url{https://github.com/NOEL-MNI/deepFCD}},
  doi = {https://doi.org/10.1212/WNL.0000000000012698}
}
```

## Pre-requisites
```console
0. Anaconda Python Environment
1. Python == 3.7
2. Keras == 2.2.4
3. Theano == 1.0.4
4. ANTsPy == 0.2.7 (for MRI preprocessing)
5. PyTorch == 1.4.0 (for deepMask)
6. h5py == 2.10.0
+ app/requirements.txt
```

## Installation

```console
# install Miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda.sh
bash ~/miniconda.sh -b -p $HOME/miniconda

# create and activate a Conda environment
conda create -n deepFCD python=3.7
conda activate deepFCD

# install dependencies using Conda/pip
# for deepFCD
conda install --yes Theano=1.0.4 keras=2.2.4 -c conda-forge
# for deepMask
conda install --yes pytorch torchvision cpuonly -c pytorch
python -m pip install -r app/requirements.txt
```


## Usage
### TODO: Training routine
### Inference using Docker
```console
docker run --rm -it --init \
    --gpus=all
    --user="$(id -u):$(id -g)" \
    --volume="$PWD:/io" \
    noelmni/deep-fcd:latest \
    /app/inference.py $PATIENT_ID $T1.nii.gz $FLAIR.nii.gz /io
```

## License
<a href= "https://opensource.org/licenses/BSD-3-Clause"><img src="https://img.shields.io/badge/License-BSD%203--Clause-blue.svg" /></a>

```console
Copyright 2021 Neuroimaging of Epilepsy Laboratory, McGill University
```
