---
title: "GoogLeNet"
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
 
> ML study > CNN architecture > GoogLeNet

<script type="text/javascript" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML">
</script>

## 1. GoogLeNet


- AlexNet의 등장이후 다양한 방식의 딥러닝 network들이 연구되었고 2014년에는 조금 더 deep 해진 구조의 network이 제시되기 시작했다. GoogLeNet은 2014 ILSVRC에서 1위를 차지하였으며 10 layer 미만이었던 기존 network에서 22 layer까지 높였고 에러 rate 역시 대폭 낮추는 성과를 얻었다.


## 2. Inception module

- 일반적으로 model이 deep해지게 되면 activation 함수를 거치면서 보다 복잡한 문제를 해결할 수 있게 된다. 하지만 데이터가 한정되어 있는 경우라면 training 데이터에만 너무 특화되어 학습이 되어 test error는 오히려 높아지게 되면 overfitting 문제가 발생하게 된다. 더불어 연산량까지 엄청나게 증가할 수 있다.

- 이러한 문제를 해결하기 위해 GoogLeNet 개발자들은 Inception module을 제안한다.

<center><img src="/assets/images/cnn/google1.jpg" width="70%"  ></center>

[<center>Source</center>](https://static.googleusercontent.com/media/research.google.com/ko//pubs/archive/43022.pdf)

- 우선 previous layer에서 보다 다양한 feature를 추출하기 위해서 1x1, 3x3, 5x5 convolution과 3x3 maxpooling layer를 병렬로 통과시켰다. 

<center><img src="/assets/images/cnn/google2.jpg" width="70%"  ></center>

[<center>Source</center>](https://static.googleusercontent.com/media/research.google.com/ko//pubs/archive/43022.pdf)

- 하지만 이러한 구조의 layer가 deep해지면 연산량의 급격한 증가가 발생하기 때문에 3x3, 5x5 convolution 앞에 1x1 convolution 을 적용해 feature map을 줄여주었다. 이로써 기존의 구조를 유지하면서 연산량을 줄일수 있게 만들었다.

## 3. GoogLeNet 구조

<center><img src="/assets/images/cnn/google3.jpg" width="100%"  ></center>

[<center>Source</center>](https://static.googleusercontent.com/media/research.google.com/ko//pubs/archive/43022.pdf)

- GoogLeNet에서는 Inception module을 9개를 사용하여 모델의 구조를 위와 같이 design하였다. 이 때 파란색 유닛은 convolution layer, 빨간색은 max pooling layer, 노란색 unit은 softmax를 나타낸다.

### 3.1 Auxiliart classifier

- GoogLeNet에서 특이한 점은 Inception module이라는 개념을 도입하여 여러번 쌓았다는 점도 있지만 softmax classifier가 마지막 단에만 있는 것이 아니라 중간 layer에서도 두번 나오는 것을 볼 수 있다.

- 아무래도 layer가 깊어질수록 gradient vanishing 문제가 발생할 수 있으며 이로 인해 학습을 진행할수록 결과가 더 나빠지게 될 수도 있다.

- 따라서 저자는 중간 layer에 auxiliary classifier를 만들어 vanishing gradient 문제를 해결하였고 보다 나은 결과를 얻었다고 한다.

- 이후 test 시에는 최종단의 classifier만을 사용한다.

## 3. Classification 결과

<center><img src="/assets/images/cnn/google4.jpg" width="60%"  ></center>

[<center>Source</center>](https://static.googleusercontent.com/media/research.google.com/ko//pubs/archive/43022.pdf)

- 2014 ImageNet classifcation에서 1위를 차지하였으며 6.67% 의 에러율로 이전 network들에 비해 상당한 성능 향상을 이루었다.


## Reference
\[1]: [GoogLeNet](https://static.googleusercontent.com/media/research.google.com/ko//pubs/archive/43022.pdf)

\[2]: [GoogLeNet 정리블로그 (라온피플)](https://blog.naver.com/laonple/220686328027)