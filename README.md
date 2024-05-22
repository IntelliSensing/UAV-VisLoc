<h1 align="center"> UAV-VisLoc: A Large-scale Dataset for UAV Visual Localization </h1>

Our technical report has been released on the [arXiv](https://arxiv.org/abs/2405.11936).

## 0. Table of Contents

* [Introduction](#1-introduction)

* [About Dataset](#2-about-dataset)

  * [Overall Dataset](#21-overall-dataset) 

  * [Dataset Example](#22-dataset-example)

* [Contributions](#3-contributions)

* [Citation](#4-citation)

## 1. Introduction
We unify the definition of visual localization methods for UAVs in real scenarios and propose a dataset as a benchmark for the visual localization task. The UAV can obtain its location coordinates by matching the UAV image with the satellite map when losing its GNSS coordinates. To construct the benchmark dataset, we collect a sequence of images on the UAV flight track in our dataset, and we further collect an orthorectified remote sensing map covering a large geographic area in which every pixel is labeled with coordinates.

The dataset collecting process is shown in Fig. 1. The task is defined as a UAV obtaining the coordinates of its current location by matching the down image with the satellite map when losing its GNSS coordinates.


| ![fig1.png](https://github.com/IntelliSensing/UAV-VisLoc/blob/main/img/fig1.png) | 
|:--:| 
| *Fig. 1 The dataset collecting process.The red point in the coordinate system represents the projection of the drone's current location on the ground, i.e., the center point of the image taken by the drone. The yellow points represent the satellite map boundaries of the entire flight range.* |

## 2. About Dataset

### 2.1 Overall Dataset

You can download our overall dataset (16.4 GB) on [Google Drive](https://drive.google.com/file/d/1xYODANyilEMM3CfWh85APwkTHQeLTcCT/view?usp=sharing) or [Baidu Net Disk](https://pan.baidu.com/s/13zgbP3Kjk1FDfZ47fBaC0g?pwd=rsai ).

Our overall dataset contains 6,742 drone images and 11 satellite maps, with a total size of 16.4GB. As presented in TABLE I, we provide the attributes of drone images, such as the latitude and longitude of the center point, shooting height, shooting date, and drone heading angle (Phi). The resolution of drone images is roughly 0.1 m to 0.2 m per pixel. We further provide the GPS latitude and longitude ranges for 11 satellite maps. One satellite map can encompass various terrains, such as cities, towns, farms, and rivers, and with a spatial resolution of 0.3 m. 


| ![table2.png](https://github.com/IntelliSensing/UAV-VisLoc/blob/main/img/table2.png)| 
|:--:| 
| *TABLE I: IMAGE ATTRIBUTE COMPOSITION FOR THE UAV-VisLoc DATASET.* |



The dataset contents are as follows:

| Drone Images | Satellite Maps | Cites | Categories |
| ------------ | -------------- | ----- | ---------- |
| 6,742        | 11             | 11    | 7          |


More detailed file structure:

```
├── UAV-VisLoc/
│   ├── satellite_coordinates_range.csv   /* format as: filename latitude longitude
│   ├── 01/
│       ├── drone/                    /* Drone Images
│           ├── 01_0001.JPG
│           ├── 01_0002.JPG
│           ├── 01_0003.JPG
|           ...
│       ├── satellite01.tif              	   /* Satellite Maps
│       ├── 01.csv			   		   /* format as: filename latitude longitude height ···
│   ├── 02/
│       ├── drone/                     /* Drone Images
│           ├── 02_0001.JPG
│           ├── 02_0002.JPG
│           ├── 02_0003.JPG
|           ...
│       ├── satellite02.tif               		/* Satellite Maps
│       ├── 02.csv				        /* format as: filename latitude longitude height ···
│   ├── 03/
│       ├── drone/                      /* Drone Images
│           ├── 03_0001.JPG
│           ├── 03_0002.JPG
│           ├── 03_0003.JPG
|           ...
│       ├── satellite03.tif              	    /* Satellite Maps
│       ├── 03.csv						/* format as: filename latitude longitude height ···
```

### 2.2 Dataset Example

You can download our dataset example (2.04 GB) on [Google Drive](https://drive.google.com/file/d/16tY7tPZiNIoyAhknvyXnp0jAfccIcHtL/view?usp=sharing) or [Baidu Net Disk](https://pan.baidu.com/s/1QPnTwZaW8pT6fzjXPo1SFQ?pwd=rsai).

We further provide a high-quality dataset sample, comprising carefully selected UAV images that exhibit minimal coordinate error and feature a diverse range of topographical elements, with a total size of 2.04 GB

As shown in Fig. 2, each satellite map downloaded from Google Maps contains all UAV images captured by a single drone flight, which may encompass various terrains such as cities, towns, farms, and rivers. 

| ![fig2.png](https://github.com/IntelliSensing/UAV-VisLoc/blob/main/img/fig2.png) | 
|:--:| 
| *Fig. 2 An example of drone images and satellite map. The red dots in the satellite map represent the center points of drone images. The satellite map encompasses various terrains such as cities, towns, farms, and rivers. We also show the drone images of these terrains.* |

Detailed File Structure：

```
├── UAV-VisLoc/
│   ├── satellite_coordinates_range.csv   /* format as: filename latitude longitude
│   ├── 03/
│       ├── drone/                      /* drone images
│           ├── 03_0001.JPG
│           ├── 03_0002.JPG
│           ├── 03_0003.JPG
|           ...
│       ├── satellite03.tif              	    /* satellite map
│       ├── 03.csv						/* format as: filename latitude longitude height ···
```

## 3. Contributions

The contributions of this dataset are as follows：

1. **Fixed-wing Drone Images.** Fixed-wing UAVs with long endurance and high flight altitude are now widely used in surveying and mapping, agriculture, and reconnaissance industries. Therefore, in addition to multi-rotor UAVs, our dataset is supplemented with drone images captured at higher altitudes by fixed-wing UAVs to accommodate multi-domain model training and testing.
2. **Multi-terrain Drone Images.** Our dataset contains drone images of various geomorphological texture features, such as villages, towns, farms, cities, rivers, hills, etc.
3. **Multi-height and Multi-heading-angle Drone Images.** Our dataset contains drone images at different altitudes, with both low-altitude urban scenes and high-altitude field scenes. Our dataset also contains drone heading angle information, which benefits subsequent related studies.
4. **Large-scale Visual Localization Dataset.** This dataset provides a sufficient amount of data to support the training and testing of models.

## 4. Citation

If you find this repository useful for your publications, please consider citing our paper.

```LaTeX
@article{xu2024uavvisloc,
      title={UAV-VisLoc: A Large-scale Dataset for UAV Visual Localization}, 
      author={Xu, Wenjia and Yao, Yaxuan and Cao, Jiaqi and Wei, Zhiwei and Liu, Chunbo and Wang, Jiuniu and Peng, Mugen},
      year={2024},
      journal={arXiv preprint arXiv:2405.11936},
}
```

