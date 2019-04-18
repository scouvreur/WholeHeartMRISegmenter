# Whole Heart MRI Segmenter

This data is from the MICCAI 2016 [challenge](http://segchd.csail.mit.edu/data.html) HVSMR 2016: MICCAI Workshop on Whole-Heart and Great Vessel Segmentation from 3D Cardiovascular MRI in Congenital Heart Disease.

[NiftyNet Docs](https://niftynet.readthedocs.io/en/dev/)

More details on the parameters in the [config file](https://niftynet.readthedocs.io/en/dev/config_spec.html#loss-type).

## Setup

```bash
conda create -n niftynet-dev
conda activate niftynet-dev
conda install tensorflow-gpu==1.12 yaml
pip install niftynet opencv-python scikit-image simpleitk pyyaml
```

## Data and Labels

Label | Axial | Coronal | Sagittal | Comments
:----:|:-----:|:-------:|:--------:|:--------:
n/a | ![](assets/a.png) | ![](assets/c.png) | ![](assets/s.png) |
`A` | ![](assets/a_label_a.png) | ![](assets/c_label_a.png) | ![](assets/s_label_a.png) | `num_classes=3`
`B` | ![](assets/a_label_b.png) | ![](assets/c_label_b.png) | ![](assets/s_label_b.png) | `num_classes=5`

Explanation of the labels in ITKSnap:

Label | 3D View | ITKSnap Labels | Anatomincal explanation
:----:|:-------:|:--------------:|:-----------------------
`A` | ![](assets/label_a.png) | ![](assets/labels_a.png) | <ul><li>`Label 1`: Myocardium</li><li>`Label 2`: Blood Pool</li></ul>
`B` | ![](assets/label_b.png) | ![](assets/labels_b.png) | <ul><li>`Label 1`: Myocardium</li><li>`Label 2`: Blood Pool</li></ul>

## Training

To start training, within the folder use:

```bash
net_segment train -c config.ini
```

It is recommended to use around `max_iter = 2000` to reach good results.

## Inference

To perform inference on the data in `testing/`, you can use:

```bash
net_segment inference -c config.ini
```

You can select the iteration checkpoint from training to perform inference on using `inference_iter`. Outputted segmentations will be placed in the directory specified in `save_seg_dir`, with the original name and the posfix specified in `output_postfix`.
