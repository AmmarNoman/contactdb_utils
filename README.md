# contactdb_utils
Python and ROS (C++) utilities for the ContactDB dataset
ContactDB is a large-scale dataset of detailed contact maps recorded from functional human grasps of household objects. It includes 50 objects, 50 participants, and 2 functional intents.

## Dataset Download links:
- [Contact Maps (Textured Meshes) (11.5 GB)](https://www.dropbox.com/sh/gzwk21ssod63xdl/AAAJ5StPMS2eid2MnZddBGsca?dl=0)
- [Data (91 GB)](https://www.dropbox.com/sh/yjp1s73ollrfafi/AAATWS-1l-MzUcNtahR36fB-a?dl=0): RGB-D-Thermal images, object 6-DOF poses and image masks, textured meshes.
- [3D Models (180 MB)](https://www.dropbox.com/sh/jdndpjhmq9pabgi/AADRBXURc97_tPsQKCy1Zj60a?dl=0)
- [Voxelized Contact Maps (18 GB)](https://www.dropbox.com/sh/x5ivxw75tvf6tax/AADXw7KRWbH3eEofbbr6NQQga?dl=0): Data needed for training and evaluating the 3D deep learning models.
- [Raw ROS bagfiles (1.46 TB)](https://www.dropbox.com/sh/hn90i9qglddnfpb/AABfB3pd34nkEF7_usktvVLMa?dl=0): Compressed 30 Hz RGB-D-Thermal data streams. See [this file](docs/rosbags.md) for documentation on how to process them.

## Visualizing Contact Maps
You will need to download the contact maps.

## Citation
```
@inproceedings{brahmbhatt2018contactdb,
  title={{ContactDB: Analyzing and Predicting Grasp Contact via Thermal Imaging}},
  author={Samarth Brahmbhatt and Cusuh Ham and Charles C. Kemp and James Hays},
  booktitle={IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2019},
  note={\url{https://contactdb.cc.gatech.edu}}
}
```
