---
title: "Touch Communication"
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

> Development > Touch Application > SVM based Touch Communication

<script type="text/javascript" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML">
</script>

## 1. SVM based Touch Communication

- 기존 capacitor에 charge를 축적한 뒤 threshold level로 터치 여부를 판단하는 대신 SVM based touch system을 적용하면 추가적인 sensing layer 없이도 팜리젝션이 가능했다.

- 그렇다면 이러한 시스템을 사용하여 단순히 필기, 그림이외의 다른 용도로 사용할 수 있는 방법을 생각해보자. 터치 디바이스에서 필기를 하다가 스타일러스를 통해 특정한 데이터를 서로 주고 받을 수 있다면 굉장히 유용해질 것이다. 

<center><img src="/assets/images/touch/svmComm1.jpg" width="67%"  ></center>
[<center>Source</center>](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8930472)

- 이 전에도 이와 같은 연구가 이루어졌지만 일반적인 터치 시스템에서는 데이터를 전송할 때 터치와 비터치를 반복하며 bit 단위로 전송이 가능했다. 또한 일반적인 터치와 구분을 하기 위해 위 그림과 같이 Initial Code 와 Terminal Code가 필요했다. 이로인해 데이터 전송속도가 굉장히 낮은 수준이었으면 손이 터치가 되었을 경우 Initial code와 혼동될 여지가 있다.

<center><img src="/assets/images/touch/svmComm2.jpg" width="60%"  ></center>
[<center>Source</center>](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8930472)

- 반면 SVM based Touch system에서는 터치와 비터치뿐 아니라 스터일러스 까지 3가지의 경우를 구분할 수 있다. 따라서 위 그림과 같이 Initial code와 Terminal Code에 stylus touch (2) 를 넣어주게 되면 실제 터치시스템에서는 0(비터치) 과 1(터치)의 경우만 존재하기 때문에 이와 구분하기 위해 필요했던 긴 code를 2 trits로 바꿀 수 있다. 따라서 기존 방식보다 훨씬 더 빠른 데이터 전송이 가능하며 보다 손이 터치가 되는 경우에도 robust한 시스템을 구축할 수 있다.

## 2. SVM based Touch Communication 결과

<center><img src="/assets/images/touch/svmComm3.jpg" ></center>
[<center>Source</center>](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8930472)

- 위 그림은 비터치(0), 터치(1), 스타일러스 터치(2) 에 대한 V<sub>Tx</sub>, Data, V<sub>ST</sub> (스타일러스 파형) 을 나타낸 것이다.

<center><img src="/assets/images/touch/svmComm4.jpg" ></center>
[<center>Source</center>](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8930472)

- 앞선 파형의 time 축을 길게 보면 다음 그림과 같다. 각각 Initial Code, Data, Terminal Code 에 대한 analog 파형을 캡처한 사진이다. 의도한 바와 같이 정상적으로 동작하며 구분가능한 것을 확인할 수 있다.

<center><img src="/assets/images/touch/svmComm5.jpg" ></center>
[<center>Source</center>](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8930472)

- 마지막으로 실제 어플리케이션을 만들어 실험한 결과이다. Text 전송, Image 전송에 대해 제대로 동작하는 것을 볼 수 있으며 stylus 끼리 구분도 가능하게끔 만들 수 있다.


## Reference
\[1]: [SVM based Touch Communication](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8930472)






<br><br>
