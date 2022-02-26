### One thing one click（CVPR 2021）

> 论文标题：One Thing One Click: A Self-Training Approach for Weakly Supervised 3D Semantic Segmentation
> 论文地址：[https://arxiv.org/pdf/2104.02246.pdf](https://openaccess.thecvf.com/content/CVPR2021/papers/Liu_One_Thing_One_Click_A_Self-Training_Approach_for_Weakly_Supervised_CVPR_2021_paper.pdf)
> 作者单位：The Chinese University of Hong Kong, The University of Hong Kong
> 代码地址：[https://github.com/liuzhengzhe/One-Thing-One-Click]
> 一句话读论文：They propose a novel two-stage detection network for accurate 3D object detection through a two-step strategy of point-voxel feature aggregation.

![img](https://pic3.zhimg.com/80/v2-03fb518bb8a7c8cd5a8b0c5da4c7d496_1440w.jpg)网络框架

<img src="https://pic2.zhimg.com/80/v2-f8e43a601205fcf09fb91e187fddc73d_1440w.jpg"

alt="KITTI testset 实验结果" style="zoom:50%;" />

整体框架属于two-stage，有两个核心内容，第一个voxel feature → keypoints feature，第二个keypoints feature → proposal/grid feature。

- **voxel feature → keypoints feature**。将大量的voxel feature 整合在少量的keypoints上，整合的过程包括了：原始raw points feature + multi-scale voxel feature + bev feature；

> Our proposed PV-RCNN-v1 first aggregates the voxel-wise scene features at multiple neural layers of 3D voxel CNN into a small number of keypoints, which bridge the 3D voxel CNN feature encoder and the proposal refinement network.

- **keypoints feature → proposal/grid feature**。这一步其实就是利用之前整合的keypoints feature对每一个proposal做RoI Grid Pooling。只是需要额外注意的是，这个的grid 半径是多尺度的，作者认为这种方式可以提取更丰富的proposal feature。

> In this step, we propose keypoint-to-grid RoI feature abstraction to generate accurate proposal-aligned features from the keypoint features for fine-grained proposal refinement.





- 

![介绍1](https://s2.loli.net/2022/02/21/tBmdCEiu82ZfLpn.png)

![介绍2](https://s2.loli.net/2022/02/21/fQbsl2rYGk4DLwa.png)