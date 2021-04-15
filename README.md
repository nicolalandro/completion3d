![![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/12pRi8IwOvYCW0doU3XQlN1DtIWLqc_vX?usp=sharing)
# AtlasNet
This is a fork in witch I try to configure and use AtlasNet. The original readme is [there](OLD_README.md).

## Configure lib and environment
```
# official
# you need python and cuda (so an Nvidia GPU)
python3.6 -m venv comp3d_venv
source comp3d_venv/bin/activate
pip install -r requirements/data-requirements.txt
pip install -r requirements/pytorch-requirements.txt

# compile chamfer
cd pytorch/utils/chamfer
python setup.py install
cd ../../../

# compile emd
cd pytorch/utils/emd/src
chmod +x make.sh
./make.sh
cd ../
python build.py
cd ../../../

# my extra
pip install jupyter
pip install matplotlib
```

## How to use a trained model

* you can find data sample (.h5) and trained (.pth.tar) model at [this release](https://github.com/nicolalandro/completion3d/releases/tag/0.1) 
* run
```
cd pytorch
jupyter notebook
firefox http://localhost:8888/notebooks/AtlasNet.ipynb
```

## Train

* download dataset from [this link](https://completion3d.stanford.edu/)
* run

```
cd pytorch
# you mast edit shared/datasets/shapenet.py 
# args.DATA_PATH = '/your/dataset/path/Completion3D/%s' % (args.dataset)
./run.py
```
