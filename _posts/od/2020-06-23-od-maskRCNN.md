---
title: "Mask RCNN"
date: 2020-06-29
category:
  - object detection
tag :
  - object detection
sidebar:
  nav: sidebar-odTwostage
mathjax: "true"
author_profile: false
toc: true
toc_label: "Contents"
toc_icon: "cog"
toc_sticky: true
header:
  overlay_image: /assets/images/dataScience.jpg
  overlay_filter: 0.5
comments: true
---

> ML study > Object Detection > Two stage detection

<script type="text/javascript" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML">
</script>

# Mask RCNN
- mask RCNN 은 그동안의 object detection model이 물체를 box로만 예측하던 것에서 벗어나 pixel단위로 segmentation까지 하여 object detection을 가능하도록 만들었다.

## 1. Mask RCNN 동작

<center><img src="/assets/images/od/survey13-fasterRCNN.jpg" ></center>

<center><img src="/assets/images/od/survey13-maskRCNN.jpg" ></center>

- Mask RCNN은 ROI pooling 이전의 layer는 Faster RCNN 구조와 동일하며 이후 mask를 예측하는 branch를 추가하여 segmentation까지 예측가능하게 하였다.


- 이과정에서 기존의 ROI pooling 을 하면 feature map과 ROI 사이에 misalign이 box를 예측할 때는 큰 문제가 되지 않았지만 segmentation에서는 정확한 예측이 어렵게 되는 문제가 있다. 

<center><img src="/assets/images/od/maskRCNN03.jpg" ></center>

- 따라서 논문에서는 pooling 시에 misalign 된 부분은 단순히 반올림해서 적용하는 것이 아니라 bilinear interpolation 방식으로 위 그림과 같이 ROI와 feature map이 서로 겹치는 비율을 고려해서 pooling을 진행하여 보다 정확한 pooling이 이루어지도록 하였다. 아래 그림은 조금더 직관적으로 ROI align 과정을 표현한 그림이다.

 <center><img src="/assets/images/od/ROIblog.jpg" ></center>


## 2. Mask RCNN 결과

-ROI align 적용을 통해 mask mAP 성능 뿐만 아니라 bounding box mAP 성능까지 향상시켰다.

<center><img src="/assets/images/od/maskRCNNT02.jpg" ></center>

- 다음 그림은 mask RCNN을 MS COCO dataset에 적용한 그림이며 5 fps로 구동이 가능하다고 한다.

<center><img src="/assets/images/od/maskRCNN05.jpg" ></center>




## Reference
\[1]: [Deep Learning for Generic Object Detection: A Survey](https://doi.org/10.1007/s11263-019-01247-4)

\[2]: [Mask RCNN 논문](https://arxiv.org/pdf/1703.06870.pdf)

\[2]: [Mask RCNN 정리 블로그](https://cdm98.tistory.com/33)



<br><br>
