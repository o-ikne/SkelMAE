# **SkelMAE**
This repository contains the source code for our paper:
**Skeleton-based Self-Supervised Feature Extraction for Improved Dynamic Hand Gesture Recognition**

![hippo](images/skelmae_approach.jpg)

## **Updates**
- code will be available soon

## **Installation**
Create and activate conda environment:
```
conda create -n skelmae python=3.10
conda activate skelmae
```

Install all dependencies:
```
pip install -r requirements.txt
```

## Training
Dowload the evaluation datasets:
- [**Briareo**](https://aimagelab.ing.unimore.it/imagelab/page.asp?IdPage=31)
- [**IPN Hand**](https://gibranbenitez.github.io/IPN_Hand/)
- [**SHREC'17**](http://www-rech.telecom-lille.fr/shrec2017-hand/).
    
### Hand Pose Extraction
We use [MediaPipe](https://developers.google.com/mediapipe) framework to extarct hand poses from RGB images (for subsets (training,validation and testing).

- For training set:
```
python extract_hand_poses.py  --data_dir ./Path/to/IPN_Hand/ 
                              --annotations_file ./Path/to/IPN_train_annotations.txt 
                              --subset training-set
                              --save_dir ./datasets/IPN_Hand/Landmarks/
```
- For testing set
```
python extract_hand_poses.py  --data_dir ./Path/to/IPN_Hand/ 
                              --annotations_file ./Path/to/IPN_test_annotations.txt 
                              --subset test-set
                              --save_dir ./datasets/IPN_Hand/Landmarks/
```

### Training

```
bash train.sh --config_file configs/ipn_hand_config.yaml
```

## Evaluation

```
bash eval.sh --config_file configs/ipn_hand_config.yaml
```

## Citation
If you find this repo useful, please consider citing our paper

```ref```

We thank [MAE](https://github.com/facebookresearch/mae) and [STGCN](https://github.com/yysijie/st-gcn) for making their code available
