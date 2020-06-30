---
title: "Cascade R-CNN"
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

# Cascade RCNN
- 그 동안 object detection의 모델이 하나의 detector를 가지고 판단을 했다면 Cascade RCNN은 이름과 같이 detector를 여러번 쌓아서 판단을 하도록하여 성능을 개선시키겠다는 논문이다.

## 1. Cascade RCNN 동작

<center><img src="/assets/images/od/cascadeRCNN03.jpg" ></center>

- 그림 (a)와 같이 기존의 faster RCNN에서는 Image 가 Conv 네트워크를 통과하고 RPN에서 나온 region에 따라 pooling을 해준 뒤 하나의 classifier가 물체를 detect하는 방식이었다.

- 그림 (b) 는 (a) 와 training과정은 동일하지만 test시에 처음 만들어낸 BB를 다시 동일한 classifier에 넣는 과정을 반복하여 좀 더 정확한 task를 수행하도록 고안된 구조이다. 실제로 성능향상을 보여주기는 하지만 3번 이상에서는 큰 의미가 없었고 극적인 효과는 없었다고 한다.


- 그림 (c) 는 classifier를 하나만 쓰는 것이 아니라 여러개를 각각 다른 IOU기준으로 training 한 뒤에 test시 모든 결과물을 ensemble 하는 방식이다. 성능향상에 도움을 주었으나 BB proposal 개선에는 한계가 있었다.

- 제안하는 Cascade RCNN은 그림 (d) 와 같은 구조로 이전의 classifier에서 예측한 BB를 다음 classifier로 넘겨주어 여러개의 서로다른 IOU 기준으로 training 된 classifier를 쌓아 예측하는 구조이다. 이 때 classifier는 뒷 단으로 갈수록 높은 기준의 IOU를 사용한다. 이렇게 되면 classification 성능 뿐 아니라 BB 값까지 정확도를 높일 수 있다고 한다. 



## 2. Cascade RCNN 결과

- Cascade를 적용시킨 결과 아래와 같이 향상된 mAP를 보였다.

<center><img src="/assets/images/od/cascadeRCNNT01.jpg" ></center>

- 아무래도 classifier를 여러개를 쓰다보니 기존 base 구조보다 속도저하가 불가피한데 논문에서는 RPN에 비하면 computation cost가 비교적 작은 수치라고 한다. 아래는 training과 test시 속도를 비교한 표이다.

<center><img src="/assets/images/od/cascadeRCNNT01.jpg" ></center>



## Reference
\[1]: [Deep Learning for Generic Object Detection: A Survey](https://doi.org/10.1007/s11263-019-01247-4)

\[2]: [Cascade RCNN 논문](https://arxiv.org/pdf/1712.00726.pdf)





<br><br>
