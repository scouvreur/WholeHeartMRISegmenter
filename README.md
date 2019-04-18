# HVSMR 2016: MICCAI Workshop on Whole-Heart and Great Vessel Segmentation from 3D Cardiovascular MRI in Congenital Heart Disease

This data is from the MICCAI 2016 [challenge](http://segchd.csail.mit.edu/data.html).

[NiftyNet Docs](https://niftynet.readthedocs.io/en/dev/)

More details on the parameters in the [config file](https://niftynet.readthedocs.io/en/dev/config_spec.html#loss-type).

## Setup

```bash
conda create -n niftynet-dev
conda activate niftynet-dev
conda install tensorflow-gpu==1.12 yaml
pip install niftynet opencv-python scikit-image simpleitk pyyaml
```

## Data and labels

Label | Axial | Coronal | Sagittal | Comments
:----:|:-----:|:-------:|:--------:|:--------:
   | ![](assets/a.png) | ![](assets/c.png) | ![](assets/s.png) |
`A` | ![](assets/a_label_a.png) | ![](assets/c_label_a.png) | ![](assets/s_label_a.png) | in config use `num_classes = 3`
`B` | ![](assets/a_label_b.png) | ![](assets/c_label_b.png) | ![](assets/s_label_b.png) | in config use `num_classes = 5`

## Training

```bash
net_segment train -c config.ini
```

## Inference

```bash
net_segment inference -c config.ini
```
