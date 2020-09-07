---
title: "VGGNet"
date: 2020-09-01
category:
  - CNN
tag :
  - CNN
sidebar:
  nav: sidebar-cnn
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
 
> ML study > CNN architecture > VGGNet

<script type="text/javascript" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML">
</script>

## 1. VGGNet


- 2014 ILSVRC에서 우승은 GoogLeNet이 차지하였지만 굉장히 근소한 차이로 2위를 차지한 것이 바로 VGGNet이다. 1위외에는 크게 기억에 남지 않는 것이 일반적이지만 VGGNet은 에러율 자체도 1위와 큰 차이가 나지 않았을 뿐아니라 훨씬 간단한 구조로 이루어져 있어져 있어 큰 주목을 받았다.


## 2. VGGNet 구조



- VGGNet의 구조는 AlexNet과 크게 다르지 않다. 다만 조금 더 layer를 deep하게 쌓았고 convolution을 적용할 때 5x5, 7x7 filter를 사용하지 않고 3x3으로만 사용하였다.

- 3x3 filter를 사용함으로써 parameter를 줄였고 한정된 자원안에서 보다 더 깊은 network을 구현가능하게 하였다.

<center><img src="/assets/images/cnn/vggnet1.jpg" width="70%"  ></center>

[<center>Source</center>](https://arxiv.org/pdf/1409.1556.pdf)

- 저자들은 위 표와 같이 A - E 까지 차례로 layer 수를 높여가며 실험을 진행하였으며 그에 따른 parameter는 table 2에 나타내었다.

## 3. Training

- Training 시 다양한 scale에 대해 robust하게 만들기 위해서 384사이즈에 대해 미리 학습 시킨 후  scale을 256과 512 사이에서 무작위로 선택해 fine tuning 하였다. 

## 4. Test
- Test 시 특정한 scale로 부터 테스트하였으며  GoogLeNet처럼 multi crop을 통해 150 장의 이미지를 만들어 사용하였다.

## 5. Result

<center><img src="/assets/images/cnn/vggnet2.jpg" width="70%"  ></center>

[<center>Source</center>](https://arxiv.org/pdf/1409.1556.pdf)

- Network의 깊이를 늘려가며 실험한 결과 A에서 E로 갈수록 error rate이 향상되는 것을 볼 수 있으며 다양한 scale에 대하여 training 시켰을 때 결과가 가장 좋은 것을 확인할 수 있다.

<center><img src="/assets/images/cnn/vggnet3.jpg" width="70%"  ></center>

[<center>Source</center>](https://arxiv.org/pdf/1409.1556.pdf)

- Training set image의 size를 다양하게 하여 실험하였을 때 test에서도 여러개의 이미지 scale에 대하여 평가한 결과가 더 좋음을 알 수 있다.

- GoogLeNet 보다 훨씬 간단한 구조로 비등한 결과를 얻었으나 classifier의 앞단에 있는 dense layer들로 인해 parameter 수가 굉장히 많아졌다는 것이 가장 큰 단점으로 보인다.

## Reference
\[1]: [VGGNet 논문](https://arxiv.org/pdf/1409.1556.pdf)

\[2]: [VGGNet 정리블로그 (라온피플)](https://blog.naver.com/laonple/220749876381)