# AtlasNet
This is a fork in witch I try to configure and use AtlasNet. The original readme is [there](OLD_README.md).

## Configure lib and environment
```
# official
# you need python and cuda (so an Nvidia GPU)
python3.6 -m venv comp3d_venv
source comp3d_venv/bin/activate
pip install -r requrements/data-requirements.txt
pip install -r requrements/pytorch-requirements.txt

# compile emd
cd pytorch/utils/emd/src
chmod +x make.sh
./make.sh
cd ../
python build.py
cd ../../../

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
