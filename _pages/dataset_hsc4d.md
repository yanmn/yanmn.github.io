---
layout: single
permalink: /data-hsc4d/
title: "HSC4D: Human-centered 4D Scene Capture in Large-scale Indoor-outdoor Space Using Wearable IMUs and LiDAR"
date: 2022-06-14
author_profile: false
venue: CVPR
journal: IEEE Conference on Computer Vision and Pattern Recognition
author: "<strong>Yudi Dai<sup>1</sup></strong>, Yitai Lin<sup>1</sup>, Chenglu Wen<sup>1, *</sup>, Siqi Shen<sup>1</sup>, Lan Xu<sup>2</sup>, Jingyi Yu<sup>2</sup>, Yuexin Ma<sup>2</sup>, Cheng Wang<sup>1</sup>"
paper: "https://arxiv.org/abs/2203.09215"
project: "/publication/2022-06-22-hsc4d"
code: "https://github.com/climbingdaily/HSC4D"
videopath: "/images/HSC4D.mp4"

header:
  overlay_color: "#9EA0A3"
  # overlay_filter: rgba(0, 0, 0, 0.3)
  # overlay_image: /images/overview.png
  image_description: "A description of the image"
  actions:
    - label: "Arxiv"
      url: "https://arxiv.org/abs/2203.09215"
    - label: "CODE"
      url: "https://github.com/climbingdaily/HSC4D"
  address: "$^1$spAital Sensing and Computing Lab, School of Informatics, Xiamen Universtiy, China<br>
  $^2$Shanghai Engineering Research Center of Intelligent Vision and Imaging, ShanghaiTech Universtiy, China"


redirect_from: 
  - "/data-hsc4d.html"
---

## Dataset

### Data structure
```
Dataset root
├── campus_road
|  ├── campus_road.bvh
|  ├── campus_road_pos.csv
|  ├── campus_road_rot.csv
|  ├── campus_road.pcap
|  └── campus_road_lidar_trajectory.txt 
├── scenes
   ├── campus_road.pcd
   ├── campus_road_ground.pcd
```


### Data preprocess
- Mocap data transfer (Optional, data provided)
  - **Input**: `campus_road.bvh`
  - **Command**: 
      ```
      pip install bvhtoolbox # https://github.com/OlafHaag/bvh-toolbox
      bvh2csv campus_road.bvh
      ```
  - **Output**: `campus_road__pos.csv`, `campus_road__rot.csv`


- Point cloud mapping (Optional, data provided)
  - Write the binary pcap into txt files. Each frame is stored in a file.
    ```
    pip install ouster-sdk 
    python ouster_pcap_to_txt.py campus_road.pcap [frame_num]
    ```
  - Run a SLAM program.
    - **Input**: The frame files in the last step.
    - **Output**: `campus_road_lidar_trajectory.txt`, `campus_road.pcd` 
  
  - Coordinate alignment (Optional, data provided)
    - ***To be added***

- Process the original files to generate necessary files for optimization. You can run the following code to preprocess the `campus_road` sequence.
  ```
  python preprocess.py --fn campus_road
  ```

### Data fusion
***To be added***

### Data optimization
***To be added***


## Copyright
The HSC4D dataset is published under the [Creative Commons Attribution-NonCommercial-ShareAlike 3.0 License](https://creativecommons.org/licenses/by-nc-sa/3.0/).You must attribute the work in the manner specified by the authors, you may not use this work for commercial purposes and if you alter, transform, or build upon this work, you may distribute the resulting work only under the same license. Contact us if you are interested in commercial usage.


## Citation
```
@misc{dai2022hsc4d,
    title={HSC4D: Human-centered 4D Scene Capture in Large-scale Indoor-outdoor Space Using Wearable IMUs and LiDAR},
    author={Yudi Dai and Yitai Lin and Chenglu Wen and Siqi Shen and Lan Xu and Jingyi Yu and Yuexin Ma and Cheng Wang},
    year={2022},
    eprint={2203.09215},
    archivePrefix={arXiv},
    primaryClass={cs.CV}
}
```
