---
title: "RCNN"
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

# Faster RCNN
- Fast RCNN까지 region proposal로 selective search (SS) 알고리즘을 사용하였지만 CNN이 feature를 뽑아내는데에 큰 성공을 거두면서 Faster RCNN에서는 SS 대신 region proposal network (RPN) 를 적용하여 object detection을 구현하였다.

## 1. Faster RCNN 동작

<center><img src="/assets/images/od/survey13-2.jpg" ></center>

### RPN은 그림과 같이 feature map의 한 포인트에서 anchor라고 불리는 k개의 서로다른 크기와 비율을 가진 reference box를 만들고 anchor에 물체가 존재할 확률과 anchor box를 regression 해주는 2개의 output layer로 구성하여 training 한다. 구체적인 동작은 다음과 같다.

<!--
<center><img src="/assets/images/od/fasterRCNN03.jpg" ></center>
-->

<center><img src="/assets/images/od/fasterRCNNBlog01.jpg" ></center>



- 먼저 RPN은 동일한 backbone CNN network의 feature를 input으로 받는다.

- feature map (HxWxC) 을 CNN에 통과시켜 2개의 output layer가 HxWx2k, HxWx4k 가 되도록 구현한다.

- 첫번째 layer는 feature map의 한 point에서 만들어낸 k anchor box에 object가 있을 확률을 의미하며, 두 번째 layer는 anchor box를 regression 해줄 좌표, 크기 정보를 의미한다.

- 이 때 동일한 물체에 대해 여러개의 box가 나올 수 있으므로 물체가 있을 확률이 높은 순서대로 정렬한 후 Non maximum suppression (NMS) 을 적용하여 총 2000개의 ROI 만을 구해준다.

- 이 후의 과정은 Fast RCNN과 동일하다.


## 2. Faster RCNN 결과

Faster RCNN은 region proposal을 CNN으로 대체하며 mAP 성능을 올렸을 뿐 아니라 Test time에서는 Fast RCNN보다 10배 더 좋은 속도를 기록하였다.

<center><img src="/assets/images/od/fasterRCNNT05.jpg" ></center>



## 3. Faster RCNN 단점
 - Region proposal까지 CNN에 적용하여 성능향상을 가져왔지만 이미지마다 진행된 수백 수천 개의 ROI에 대하여 sub network를 통과시켜야 한다는 점이 문제점으로 거론되었다.



## Reference
\[1]: [Deep Learning for Generic Object Detection: A Survey](https://doi.org/10.1007/s11263-019-01247-4)

\[2]: [Faster RCNN 논문](https://arxiv.org/pdf/1506.01497.pdf)

\[2]: [Faster RCNN 정리 블로그](https://yeomko.tistory.com/17f)



<br><br>
