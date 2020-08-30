---
title: "AlexNet"
date: 2020-08-21
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
 
> ML study > CNN architecture > AlexNet

<script type="text/javascript" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML">
</script>

## 1. AlexNet


- AlexNet은 2012년 ImageNet Large Scale Visual Recognition Challenge (ILSVRC) 에서 우승하면서 유명세를 얻었다. 이전의 26% 였던 에러율을 무려 10%을 낮추었다. 2012년 이전의 알고리즘에서는 shallow 한 구조에서 개발자들이 도출한 feature를 적용하여 test 하였지만 AlexNet에서는 CNN 기반 deep learning 알고리즘을 사용하여 괄목할만한 성능향상을 가져왔다.


## 2. 구조

<center><img src="/assets/images/cnn/alexnet1.jpg" width="70%"  ></center>

[<center>Source</center>](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)

- AlexNet의 구조는 LeNet-5 의 기본 구조와 크게 다르지 않지만 nerwork가 더 deep해지고 커졌다. 이러한 구조를 학습시키기 위해 2개의 GPU를 병렬로 처리하였다.

- 총 5개의 convolution 과 3번의 fully connected layer를 거쳐 1000개의 class를 구분하기 위한 softmax 함수를 사용하였다.

- 입력 영상은 227x227x3 으로 LeNet 보다 굉장히 큰 이미지를 사용하였으며 이로 인해 첫 번째 convolutional layer의 kernel 역시 11x11x3으로 비교적 큰 사이즈를 사용하였다. stride는 4를 적용하여 55x55x96 의 feature map을 출력하도록 하였다. 이 때 stride를 크게 사용했기 때문에 추가적인 pooling 과정은 거치지 않았다.

- 두 번째 layer에선는 5x5x48 크기의 kernel을 사용하였으며 normalization 과 pooling 과정을 거쳐 27x27x256의 feature map을 얻었다.

- 이 후 3번의 convolution 과정을 거친뒤 3번의 fully connected layer를 통해 1000개의 category를 구분하게 된다.

## 3. 성능 개선

<center><img src="/assets/images/cnn/relu1.jpg" width="70%"  ></center>

[<center>Source</center>](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)

- Activation 함수로는 sigmoid나 tanh 함수 대신 ReLu를 사용하였다. 그 결과 위 그래프(실선이 relu, 점선은 tanh) 와 같이 학습속도가 굉장히 개선되는 것을 확인하였다. sigmoid나 tanh의 경우 0에서 크게 벗어나게 되면 기울기가 0이 되어 깊은 network에서 gradient vanishing 문제가 있었는데 relu에서는 0 이상일 때 constant 한 미분 값을 갖도록하여 vaninshing 문제를 없애고 빠르게 학습하는 것을 도와준다. 또한 0 이하인 경우는 출력을 0으로 saturation 시켜 non linearity를 주었고 동시에 sparse 한 output을 출력하도록 하여 계산이 빠르게 만들었다.  

- Pooling 방식으로는 average pooling 대신 max pooling을 사용하여 생물학적 특성과 유사하게 구성하였으며 3x3의 window와 2x2 stride를 사용하여 ovelapped 되도록 pooling을 사용하였다. 

- Convolution 결과 나온 feature map에 대해서 normalization을 수행하여 조금 더 generalization 효과를 줌으로써 에러율을 개선하였다고 한다.

- Parameter가 굉장히 많아지다보니 overfitting 문제가 생길 수 있는데 이에 대한 해결책으로 data augmentation 기법을 활용하였다. ILSVRC의 256x256 원본 데이터로 부터 무작위로 224x224 크기의 영역을 자르는 방식과 RGB 채널의 값을 조금씩 변경하여 다양한 data를 만들어 overfitting을 줄였다. Test 시에는 상하좌우 중앙으로 부터 5개의 영상을 얻고 그것을 반전하여 총 10개에 대한 softmax 평균으로 부터 output을 구했다고 한다.

- 추가적으로 overfitting을 막기위해 fully conncected layer에 dropout을 적용하여 성능을 개선하였다. 

## 3. 결과

<center><img src="/assets/images/cnn/alexnet3.jpg" width="70%"  ></center>

[<center>Source</center>](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)

- ILSVRC data에 대한 실험결과 이전에 가장 좋았던 model (SIFT+Fvs) 보다 Top-5 test에서 10% 정도의 에러율을 낮춘 것을 확인할 수 있다.

- CNN 앞에 붙은 숫자는 동일한 netwokr를 여러개 사용하여 평균을 내어 예측하는 model이며 *표시는 2011 ImageNet에 대하여 pretraining 한 model이다.

<center><img src="/assets/images/cnn/alexnet2.jpg" width="70%"  ></center>

[<center>Source</center>](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)

- 실제 몇가지 image에 대한 실험결과이며 합리적인 결과를 출력하고 있는 것을 볼 수 있다.

## Reference
\[1]: [AlexNet](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)

\[2]: [AlexNet 정리(Naver)](https://blog.naver.com/laonple/220667260878)