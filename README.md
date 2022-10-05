# 3DOM-Semantic-Facade 
Benchmark dataset for facade semantic segmentation. 

![3DOM Semantic Facade dataset](3DOM_benchmark.png)

[Benchmark data](https://drive.google.com/drive/folders/1kZeNVL6-TL5oGuZfjj5wjPdxldvX_88J?usp=sharing)

_________________________________________________________________________
### 1. Dataset Description

We present a new real-world, densely-annotated, semantic segmentation benchmark for (historic) building facades that can sbe useful: 
1. for training ML/DL algorithms and 
2. image-based 3D reconstruction (SfM/MVS). 

The sequences contain high-resolution images across various cities in Italy. They depict historic building facades from the street level. The buildings, although of similar height, feature a significant diversity in architectural styles and structural characteristics spreading from traditional historic center buildings to cathedrals.

The number of images for each sequence varies. RGB images are in \*.jpg format and are
suitable for MVS reconstruction. Corresponding pixel-level
GT labels  are named \*_l.png

|Dataset name  |  original resolution  | camera name |
|--|--|--|
| [Albergati, Bologna Portici] |4608 x 3072 |NIKON D3100|
| [Campidoglio, Chigi] |4416 x 3312 |Canon PowerShot G10|
| [Lecce Duomo, Lecce Teatini] |6000 x 4000 |NIKON D5300|
| Piazza Navona |4000 x 3000 |SAMSUNG ST45 (mobile)|
| Piazza Trento Duomo |6048 x 4032 |NIKON D3X|



*Note:* Piazza Navona sequence is not suitable for 3D reconstruction 
since (1) images do not have sufficient overlap and (2) some labels 
refer to the undistorted version of the image (\*_undistort.png). 
Can be used for training purposes though. 

_________________________________________________________________________
### 2. Class nomenclature

The dataset aims at a generic facade segmentation and identification of the basic components; each class should have a clear and unambiguous semantic meaning, while all classes should be unique with respect to their geometric characteristics and visual appearance. Therefore, five semantic classes were defined, namely “wall”, “sky”, “obstacle”, “window”, and “door”; the class “obstacle” includes all parts of the scene that are typically unwanted in photogrammetric scenarios, e.g., moving objects such as cars, bikes, and pedestrians, but also trees, vegetation, traffic signs, and the street itself. Such a nomenclature facilitates the isolation of objects considered noise, e.g., the sky and obstacles, while enabling the selective reconstruction of specific semantic classes of interest such as the facade walls or the openings “window” and “door”.

Semantic labelling was performed manually in-house.
Mixed color pixels occurring between class borders 
are given (0,0,0) value, i.e., black.

|class name  |  RGB values  |
|--|--|
| facade |(0,0,255) |
| window |(0,255,0) |
| door |(255,0,255) |
| sky |(255,255,0)|
| obstacle  |(255,0,0) |

_________________________________________________________________________
### 3. Credits
This dataset is publicly available for research purposes.
If you use this dataset for your research, please cite our articles:

   
    
    @article{stathopoulou2019semantic,
      title={Semantic photogrammetry: boosting image-based 3D reconstruction with semantic labeling},
      author={Stathopoulou, Elisavet Konstantina and Remondino, Fabio},
      journal={International Archives of the Photogrammetry, Remote Sensing and Spatial Information Sciences},
      volume={42},
      number={2},
      pages={W9},
      year={2019}
    }
    
    @article{stathopoulou2019multi,
      title={Multi-view stereo with semantic priors},
      author={Stathopoulou, Elisavet Konstantina and Remondino, Fabio},
      journal={International Archives of the Photogrammetry, Remote Sensing and Spatial Information Sciences},
      volume={42},
      number={2/W15},
      year={2019}
    }
    
    @article{stathopoulou2021semantically,
      title={Semantically derived geometric constraints for MVS reconstruction of textureless areas},
      author={Stathopoulou, Elisavet Konstantina and Battisti, Roberto and Cernea, Dan and Remondino, Fabio and Georgopoulos, Andreas},
      journal={Remote Sensing},
      volume={13},
      number={6},
      pages={1053},
      year={2021},
      publisher={Multidisciplinary Digital Publishing Institute}
    }
    
    @PhdThesis{stathopoulou2022PhD,
      title={Integrating scene priors in Multiple View Stereo},
      author={Stathopoulou, Elisavet Konstantina},
      year={2022},
      school={National Technical University of Athens}
    }
