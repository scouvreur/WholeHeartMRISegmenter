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


## Training

```bash
net_segment -c config.ini train
```

## Testing

```bash
net_segment -c config.ini evaluation
```

## Inference

```bash
net_segment -c config.ini inference
```