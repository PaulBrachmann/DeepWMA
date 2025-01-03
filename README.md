
# DeepWMA (Deep White Matter Analysis)

This code implements a deep learning tractography segmentation method (DeepWMA) that allows fast and consistent white matter fiber tract identification, as described in the following paper:

    Fan Zhang, Suheyla Cetin Karayumak, Nico Hoffmann, Yogesh Rathi, Alexandra J. Golby, and Lauren J. O’Donnell.
    Deep white matter analysis (DeepWMA): fast and consistent tractography segmentation.
    Medical Image Analysis 65 (2020): 101761

This version updates the code to the latest Tensorflow 2 environment, TF 2.6, and new h5py versions.

## Installation

1. Install 3D Slicer (https://www.slicer.org) and SlicerDMRI (http://dmri.slicer.org)
2. Clone this repository
3. Inside of this repository, run:

```sh
conda create -n DeepWMA python=3.10.6 -y
conda activate DeepWMA

pip install git+https://github.com/SlicerDMRI/whitematteranalysis.git@165cfcdb321adf7177938d7c2f6723500cc4c9eb
pip install tensorflow~=2.3
pip install -U scikit-learn
	
curl -LO https://github.com/zhangfanmark/DeepWMA/releases/download/v0.1-alpha/SegModels.zip
tar -xzvf SegModels.zip
rm SegModels.zip

curl -LO https://github.com/zhangfanmark/DeepWMA/releases/download/v0.1-alpha/TestData.zip
tar -xzvf TestData.zip
rm TestData.zip

chmod +x ./run_DeepWMA.sh
```

Then configure the `run_DeepWMA.sh` file:

- Adjust paths, use the `Slicer.app/Contents/MacOS/Slicer` executable if you are on MacOS

## Example

See the following script for instructions:

```sh
sh run_DeepWMA.sh
```

**Please cite the following papers:**

    Fan Zhang, Suheyla Cetin Karayumak, Nico Hoffmann, Yogesh Rathi, Alexandra J. Golby, and Lauren J. O’Donnell.
    Deep white matter analysis (DeepWMA): fast and consistent tractography segmentation.
    Medical Image Analysis 65 (2020): 101761

    Fam Zhang, Ye Wu, Isaiah Norton, Yogesh Rathi, Nikos Makris and Lauren J. O’Donnell.
    An anatomically curated fiber clustering white matter atlas for consistent white matter tract parcellation across the lifespan.
    NeuroImage, 2018 (179): 429-447

    Fan Zhang, Thomas Noh, Parikshit Juvekar, Sarah F Frisken, Laura Rigolo, Isaiah Norton, Tina Kapur, Sonia Pujol, William Wells III, Alex Yarmarkovich, Gordon Kindlmann, Demian Wassermann, Raul San Jose Estepar, Yogesh Rathi, Ron Kikinis, Hans J Johnson, Carl-Fredrik Westin, Steve Pieper, Alexandra J Golby, Lauren J O'Donnell.
    SlicerDMRI: Diffusion MRI and Tractography Research Software for Brain Cancer Surgery Planning and Visualization.
    JCO Clinical Cancer Informatics 4, e299-309, 2020.

    Isaiah Norton, Walid Ibn Essayed, Fan Zhang, Sonia Pujol, Alex Yarmarkovich, Alexandra J. Golby, Gordon Kindlmann, Demian Wassermann, Raul San Jose Estepar, Yogesh Rathi, Steve Pieper, Ron Kikinis, Hans J. Johnson, Carl-Fredrik Westin and Lauren J. O'Donnell.
    SlicerDMRI: Open Source Diffusion MRI Software for Brain Cancer Research. Cancer Research 77(21), e101-e103, 2017.
