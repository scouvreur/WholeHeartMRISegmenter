# HVSMR 2016: MICCAI Workshop on Whole-Heart and Great Vessel Segmentation from 3D Cardiovascular MRI in Congenital Heart Disease

This data is from the MICCAI 2016 [challenge](http://segchd.csail.mit.edu/data.html).

[NiftyNet Docs](https://niftynet.readthedocs.io/en/dev/)

## Setup

```bash
conda create -n niftynet-dev
conda activate niftynet-dev
conda install tensorflow-gpu==1.12 yaml
pip install niftynet opencv-python scikit-image simpleitk pyyaml
```

## Data and labels

<!-- | Raw | Pre-processed |
:----:|:--------------:
![0a0ec5a23](assets/0a0ec5a23.jpg) | ![0a0ec5a23](assets/0a0ec5a23_256.jpg)
![0a810e2a1](assets/0a810e2a1.jpg) | ![0a810e2a1](assets/0a810e2a1_256.jpg)
![0c2d0b8b8](assets/0c2d0b8b8.jpg) | ![0c2d0b8b8](assets/0c2d0b8b8_256.jpg)
 -->

## Training

```bash
net_segment train -c config.ini
```

## Inference

```bash
net_segment inference -c config.ini
```