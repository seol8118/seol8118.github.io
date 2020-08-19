---
title: "Motivation & Previous Approaches"
date: 2020-08-19
category:
  - touch system
tag :
  - touch system
sidebar:
  nav: sidebar-touch
mathjax: "true"
author_profile: false
toc: true
toc_label: "Contents"
toc_icon: "cog"
toc_sticky: true
header:
  overlay_image: /assets/images/development.jpg
  overlay_filter: 0.5
comments: true
---

> Development > Motivation & Previous Approaches

<script type="text/javascript" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML">
</script>


## 1. Mutual capacitive touch 동작

<center><img src="/assets/images/touch/pcap1.jpg" ></center>

- Mutual capacitive touch 회로는 왼쪽 그림과 같이 Tx와 Rx line으로 구성된다. 이 때 각각의 라인은 서로 교차하며 capacitor를 형성하게 되는데 이것을 mutual capacitor라고 부른다.

- 오른쪽 그림은 일반적인 Mutual capacitive touch system을 나타낸 그림이다. 먼저 Excitation Driver에서 Tx 라인에 특정 pulse를 순차적으로 보내준다.

- 하나의 Tx 라인에 excited 되었을 때 Rx에 연결되어 있는 charge amplifier는 mutual capacitor의 charge를 voltage로 변환하여 출력하며 이렇게 나온 N<sub>Rx</sub> 개의 output은 multiplexer를 통해 ADC로 전달된다.

- ADC에서는 analog 값을 digital로 변환시켜 Host processor에 보내주고 이곳에서 터치 여부를 판단하게 된다.

- 따라서 모든 Tx line excited되면 모든 mutual capacitance 값을 host processor에서 계산할 수 있게 된다.

- 만약 터치 패널에 손가락이 터치가 되면 mutual capactor의 fringe field가 손가락의 ground로 빠져나가면서 capacitance가 줄어들게 되는데 이차이를 host processor가 인지하여 터치 여부를 판단할 수 있게 된다.


## 2. 터치 여부 판단

<center><img src="/assets/images/touch/pcap2.jpg" ></center>

- 조금 더 구체적으로 charge amplifier의 output 단에서 touch가 되었을 때 output이 어떻게 변화되는지 살펴보자.

- 우선 터치가 되지 않았을 때에는 Tx line에 V<sub>Tx</sub> 가 걸렸을 때 반대 방향으로 $\Delta$ V<sub>OUT-NT</sub> 만큼 감소하여 나온다.

- 반면 터치가 되었을 때는 mutual capacitance가 줄어들기 때문에 이 차이에 비례하여 V<sub>OUT</sub> 더 줄어든 값만큼 감소하여 나온다.

- 이 차이를 통해 터치 여부를 판단할 수 있다.

## 3. SNR 개선 방식

<center><img src="/assets/images/touch/pcap3.jpg" ></center>

- 이 때 터치의 정확도 및 signal to noise ratio (SNR) 를 높이기 위한 방식이 다양하게 연구되고 있는데 대표적으로 위 그림과 같이 Tx 라인마다 여러번의 pulse를 보내주어 charge amplifier의 feedback capacitor에 charge를 쌓은 뒤 ADC sampling을 통하여 터치여부를 판단하는 방식이 존재한다.

## 4. Stylus

<center><img src="/assets/images/touch/stylus.jpg" ></center>

- 또한 최근에는 이러한 터치패널을 이용하여 보다 정교한 작업을 위한 stylus 기술들이 많이 제안되었다.

- 가장 간단한 방식은 Passive stylus 방식으로 전기가 통하는 섬유를 stylus의 tip으로 만들어 마치 손가락이 터치가 된 것 같은 효과를 얻게 하는 방식이다. 손가락을 모방하는 방식으로 대부분의 터치패널에서 사용가능하나 손가락 크기 만큼 터치가 되어야 인식하기에 정교한 작업을 하기에는 어려움이 있다.

- 두 번째로 Active stylus 방식이 있다. 이 방식은 사람이 터치를 했을 때 charge amplifier의 output voltage 변화량이 줄어든다는 원리를 이용하여 stylus에서 Tx 파형을 sensing한 다음 그것을 inverting하여 tip을 통해 터치패널에 보내주는 방식이다. 이렇게 되면 amplifier의 output이 Tx에 의해 줄어드는 영향이 줄어들어 마치 터치가 된 것으로 인식을 하게 된다. 직접 voltage를 걸어주는 방식이기 때문에 손보다도 훨씬 작은 면적으로 터치 인식이 가능하게 되어 정교한 작업을 할 수 있다. 하지만 손과 같은 원리로 인식되기 때문에 손과 stylus를 구분하는 팜리젝션은 불가능하다.

- 마지막으로 Electro Magnetic Resonance (EMR) 방식을 사용한 stylus가 있다. EMR 방식은 일반적인 터치패널아래에 하나의 layer를 더 쌓고 그곳에서 내보내는 자기장과 stylus의 사이에서 발생하는 전자기유도에 의한 공명을 감지해서 터치여부를 판단하게 된다. 기본적인 손가락을 판단하는 시스템과는 전혀 다른 방식으로 동작하기 때문에 팜리젝션이 가능한 동시에 정교한 작업을 할 수 있지만 layer가 추가로 필요하다는 단점이 있다.

## Reference
\[1]: S. Ko, H. Shin, J. Lee, H. Jang, B.-C. So, I. Yun, and K. Lee, “Low Noise Capacitive Sensor for Multi-touch Mobile Handset’s Applications,” IEEE Asian Solid-State Circuits Conference, 4-3 (2010).





<br><br>
