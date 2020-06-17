# MERL-RAV Dataset
MERL-RAV (MERL Reannotation of AFLW with Visibility) dataset contains over 19,000 face images in a full range of head poses. Each face is manually labeled with the ground-truth locations of 68 landmarks, with the additional information of whether each landmark is unoccluded, self-occluded (due to extreme head poses), or externally occluded.

Please cite the following papers if you use this dataset in your research:
```
@inproceedings{kumar2020luvli,
  title={LUVLi Face Alignment: Estimating Landmarks' Location, Uncertainty, and Visibility Likelihood},
  author={Kumar, Abhinav and Marks, Tim K and Mou, Wenxuan and Wang, Ye and Jones, Michael and Cherian, Anoop and Koike-Akino, Toshiaki and Liu, Xiaoming and Feng, Chen},
  booktitle={CVPR},
  year={2020}
}
```
Please also consider citing the original [AFLW dataset](https://www.tugraz.at/institute/icg/research/team-bischof/lrs/downloads/aflw/)
 as well.

### Instructions
Download this repo and unzip it. Move to the project directory.
```bash
cd $PROJECT_DIR
```

Then, download the AFLW dataset by following the instructions [here](https://www.tugraz.at/institute/icg/research/team-bischof/lrs/downloads/aflw/)

The directory should look like this
```bash
 |--merl_rav_labels
 |        |-- frontal
 |        |      |--testset
 |        |      |--trainset
 |        |
 |        |-- left 
 |        |      |--testset
 |        |      |--trainset
 |        |
 |        |-- lefthalf
 |        |      |--testset
 |        |      |--trainset
 |        |
 |        |-- right
 |        |      |--testset
 |        |      |--trainset
 |        |
 |        |-- righthalf
 |               |--testset
 |               |--trainset
 |
 |
 |--aflw
 |    |--flickr
 |         |--0
 |         |--2
 |         |--3
 |
 |--common_functions.py
 |--organize_merl_rav_using_aflw_and_our_labels.py
```
If your ```aflw``` folder is located elsewhere set the path in ```input_folder``` variable of the file ```organize_merl_rav_using_aflw_and_our_labels.py```

Next execute the following command
```bash
python organize_merl_rav_using_aflw_and_our_labels.py
```

The script goes through the sub-directories of the ```merl_rav_labels``` folder and then find the corresponding image from the ```aflw``` folder. It will then create a folder named ```aflw_ours_organized``` in the same directory. This folder will have the following directories

```bash
 |--aflw_ours_organized
 |        |-- frontal
 |        |      |--testset
 |        |      |--trainset
 |        |
 |        |-- left 
 |        |      |--testset
 |        |      |--trainset
 |        |
 |        |-- lefthalf
 |        |      |--testset
 |        |      |--trainset
 |        |
 |        |-- right
 |        |      |--testset
 |        |      |--trainset
 |        |
 |        |-- righthalf
 |               |--testset
 |               |--trainset
 |
```
Each of the ```testset``` and ```trainset``` in ```merl_rav_labels``` will have the images as well as labels. The basename of the image and the ground truth labels are the same, they only differ in the name of the extension. The labels have pts extension while images have the jpg extension.

eg. The image with name ```image03891.jpg``` has the labels ```image03891.pts```

### Format of the labellings
