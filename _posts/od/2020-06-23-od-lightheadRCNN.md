---
title: "Light Head R-CNN"
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

# Light Head R-CNN
- Light Head R-CNN 은 그동안의 two stage object detection model의 속도가 one stage object detection model보다 느린 가장 큰 이유를 무거운 head 구조로 말하며 새로운 head 구조를 제시함으로써 놀라운 속도 향상을 얻었다.

## 1. Light Head R-CNN 동작

<center><img src="/assets/images/od/lightHeadRCNN02.jpg" ></center>

[<center>Source</center>](https://arxiv.org/pdf/1711.07264.pdf)

- Faster R-CNN에서 FC 이루어진 무거운 head 부분은 RFCN에서 score map이라는 개념을 도입하여 conv 네트워크 연산이 가능하게끔 만들었었다. 

- RFCN 구조로 상대적으로 Head 구조가 가벼워졌지만 class가 많아지고 풀링 사이즈가 커질수록 score map역시 늘어나는 문제가 있었다.

- 본 논문에서는 Xception이라는 가벼운 backbone network와 Large separable convolution을 통한 얇은 feature map, 가벼운 FC layer를 사용하여 위 문제들을 개선하였다.

<center><img src="/assets/images/od/lightHeadRCNN03.jpg" ></center>

[<center>Source</center>](https://arxiv.org/pdf/1711.07264.pdf)

## 2. Light Head R-CNN 결과

- Two stage 기반으로 102 fps 라는 놀라운 결과를 기록하였으며 mAP에서도 R-FCN보다 좋은 결과를 기록하였다.

<center><img src="/assets/images/od/lightHeadRCNNT08.jpg" ></center>

[<center>Source</center>](https://arxiv.org/pdf/1711.07264.pdf)


## Reference
\[1]: [Deep Learning for Generic Object Detection: A Survey](https://doi.org/10.1007/s11263-019-01247-4)

\[2]: [Light Head R-CNN 논문](https://arxiv.org/pdf/1711.07264.pdf)



<br><br>
