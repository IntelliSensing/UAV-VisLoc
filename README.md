<h1 align="center"> UAV-VisLoc: A Large-scale Dataset for UAV Visual Localization </h1>

Our technical report has been released on the [arXiv](https://arxiv.org/abs/2405.11936)

## 0. Table of Contents

* [Introduction](#1-introduction)

* [About Dataset](#2-About Dataset)
  * [Overall Dataset](#21-Overall Dataset) 

  * [Dataset Example](#22-Dataset Example)

* [Contributions ](#3-Contributions )

* [Citation](#4-Citation)

## 1. Introduction
We unify the definition of visual localization methods for UAVs in real scenarios and propose a dataset as a benchmark for the visual localization task. The UAV can obtain its location coordinates by matching the UAV image with the satellite map when losing its GNSS coordinates. To construct the benchmark dataset, we collect a sequence of images on the UAV flight track in our dataset, and we further collect an orthorectified remote sensing map covering a large geographic area in which every pixel is labeled with coordinates.

Fig. 1 shows the dataset-collecting process. The red point in the coordinate system represents the projection of the drone’s current location on the ground, i.e., the center point of the image taken by the drone. The yellow points represent the satellite map boundaries of the entire flight range.

<div align=center>
<img src="https://github.com/IntelliSensing/UAV-VisLoc/blob/main/img/fig1.png" width="60%">
</div>
## 2. About Dataset

### 2.1  Overall Dataset

Please download **overall datasets** via this [link](https://drive.google.com/file/d/1xYODANyilEMM3CfWh85APwkTHQeLTcCT/view?usp=sharing). 

Our overall dataset contains 6,742 drone images and 11 satellite maps, with a total size of 16.4GB. As presented in TABLE I, we provide the attributes of drone images, such as the latitude and longitude of the center point, shooting height, shooting date, and drone heading angle (Phi). The resolution of drone images is roughly 0.1 m to 0.2 m per pixel. We further provide the GPS latitude and longitude ranges for 11 satellite maps. One satellite map can encompass various terrains, such as cities, towns, farms, and rivers, and with a spatial resolution of 0.3 m. 

<div align=center>
<img src="https://github.com/IntelliSensing/UAV-VisLoc/img/table2.png" width="60%">
</div>

The dataset contents are as follows:

| Drone-view | Satellite-view | Cites | Categories |
| ---------- | -------------- | ----- | ---------- |
| 6742       | 11             | 11    | 7          |


More detailed file structure:

```
├── UAV-VisLoc/
│   ├── satellite_coordinates_range.csv   /* format as: filename latitude longitude
│   ├── 01/
│       ├── drone/                    /* drone-view images
│           ├── 01_0001.JPG
│           ├── 01_0002.JPG
│           ├── 01_0003.JPG
|           ...
│       ├── satellite01.tif              	   /* satellite-view image
│       ├── 01.csv			   		   /* format as: filename latitude longitude height ···
│   ├── 02/
│       ├── drone/                     /* drone-view images
│           ├── 02_0001.JPG
│           ├── 02_0002.JPG
│           ├── 02_0003.JPG
|           ...
│       ├── satellite02.tif               		/* satellite-view image
│       ├── 02.csv				        /* format as: filename latitude longitude height ···
│   ├── 03/
│       ├── drone/                      /* drone-view images
│           ├── 03_0001.JPG
│           ├── 03_0002.JPG
│           ├── 03_0003.JPG
|           ...
│       ├── satellite03.tif              	    /* satellite-view image
│       ├── 03.csv						/* format as: filename latitude longitude height ···
```

### 2.2  Dataset Example

Please download **dataset example** via this [link](https://drive.google.com/file/d/16tY7tPZiNIoyAhknvyXnp0jAfccIcHtL/view?usp=sharing). 

We further provide a high-quality dataset sample, comprising carefully selected UAV images that exhibit minimal coordinate error and feature a diverse range of topographical elements, with a total size of 2.04 GB

As shown in Fig. 2, the satellite map in the dataset sample encompasses various terrains, such as cities, towns, farms, and rivers.

<div align=center>
<img src="https://github.com/IntelliSensing/UAV-VisLoc/img/fig2.png" width="60%">
</div>

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
@misc{xu2024uavvisloc,
      title={UAV-VisLoc: A Large-scale Dataset for UAV Visual Localization}, 
      author={Wenjia Xu and Yaxuan Yao and Jiaqi Cao and Zhiwei Wei and Chunbo Liu and Jiuniu Wang and Mugen Peng},
      year={2024},
      eprint={2405.11936},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

