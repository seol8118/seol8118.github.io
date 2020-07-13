---
title: "Fast R-CNN"
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

# Fast R-CNN
- R-CNN과 SPPNet에서는 여전히 detector를 SVM이라는 별개의 네트워크로 사용한 반면 Fast R-CNN에서는 softmax classifier와 BBox regressor를 동시에 학습할 수 있는 end-to-end detector를 구현하였다.

## 1. Fast R-CNN 동작

<center><img src="/assets/images/od/survey13-1.jpg" ></center>

[<center>Source</center>](https://doi.org/10.1007/s11263-019-01247-4)

- Fast R-CNN은 R-CNN과 다르게 Image를 먼저 CNN에 통과시킨다는 점에서 SPPNet과 매우 유사하다. 이 후 Region proposal된 feature가 ROI pooling layer를 통과하는데, SPP가 여러개의 pooling layer를 통과시키고 concat 시킨 것과 달리 ROI는 1개의 pooling layer를 통과하게 된다. 이는 하나의 object에 대해서 여러개의 pooling layer를 만들면 overfitting 될 가능성과 속도저하 때문이라고 한다.

- 또한 detector로 사용했던 SVM대신 softmax classifier를 사용하여 end-to-end 연산이 가능하게 했다.

- 이렇게 하면 training 과 test 시에 시간을 많이 잡아먹은 CNN을 단 한번만 수행할 수 있기 때문에 R-CNN의 문제점을 획기적으로 단축시킬 수 있다.


## 2. Fast R-CNN 결과

Fast R-CNN은 end-to-end training으로 기존 R-CNN과 SPPNet 보다 mAP 성능을 올렸으며 Training과 Test time에서도 좋은 속도를 기록하였다.

<center><img src="/assets/images/od/fastRCNNT03.jpg" ></center>

[<center>Source</center>](https://arxiv.org/pdf/1504.08083.pdf)

<center><img src="/assets/images/od/fastRCNNT04.jpg" ></center>

[<center>Source</center>](https://arxiv.org/pdf/1504.08083.pdf)

## 3. Fast R-CNN 단점
 - 속도와 성능 향상을 가져왔지만 여전히 Region proposal로는 selective search 알고리즘을 사용하여 속도 및 성능 개선의 여지가 남아있다.



## Reference
\[1]: [Deep Learning for Generic Object Detection: A Survey](https://doi.org/10.1007/s11263-019-01247-4)

\[2]: [Fast R-CNN 논문](https://arxiv.org/pdf/1504.08083.pdf)



<br><br>
