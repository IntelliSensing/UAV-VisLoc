<h1 align="center"> UAV-Loc: A Multi-terrain Dataset for UAV Visual-localization </h1>

The practical application of UAVs is increasing, and it is crucial to ensure accurate latitude and longitude coordinates for UAVs under conditions where global navigation satellite systems are not working. Existing visual localization methods achieve autonomous visual localization without error accumulation by matching with ortho satellite images. We redefine the UAV Visual-localization task by determining the UAV's real position coordinates on a large-scale satellite map based on the captured ground-down view. To facilitate research,  we release a new dataset, UAV-VisLoc, perfectly suited for our redefined UAV Visual-localization task. 

This repository contains datasets for the **UAV Visual-localization** task. We provide the UAV_Loc dataset implementation to facilitate research on this task. Thank you for your attention.

![lct1](C:\Users\XUAN\Pictures\lct1.png)



## Table of contents

- [News](#news)
- [About Dataset](#about-dataset)
- 

## News

- **`2024/5/15`**: Our dataset is released.
- 

## About Dataset

We gather drone images from different regions in China, covering diverse topographical features, cleaning raw drone images, and sourcing satellite images from Google Maps. Key features of the dataset include fixed-wing and multi-terrain drone images and images captured at various heights and heading angles. Our dataset aims to support model training and testing by providing diverse data. 

Our dataset comprises 6742 drone images and 11 satellite maps, providing attributes such as latitude, longitude, shooting height, and shooting date. Drone maps are roughly 0.1-0.2m per pixel, satellite maps 0.3m per pixel, and 16.4GB of data.

![qs1](C:\Users\XUAN\Pictures\qs1.png)



The dataset contents are as follows:

| Drone-view | Satellite-view | Cites | Categories |
| ---------- | -------------- | ----- | ---------- |
| 6742       | 11             | 11    | 7          |

![table](C:\Users\XUAN\Pictures\table.png)



More detailed file structure:

```
├── UAV_Loc/
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
|   ...
```

