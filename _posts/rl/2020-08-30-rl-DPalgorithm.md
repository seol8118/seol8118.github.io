---
title: "Dynamic Programming Algorithm"
date: 2020-08-30
category:
  - RL
tag :
  - RL
sidebar:
  nav: sidebar-rl
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
 
> ML study > Reinforcement Learning > Dynamic Programming Algorithm

<script type="text/javascript" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML">
</script>


## 1. 동기적 Dynamic Programming

- 우리는 Dynamic programming (DP) 을 통해 최적의 정책을 찾는 방법을 알아보았다. 지난 post에서 알아본 DP는 모든 table을 동시에 업데이트 하는 방식으로 동기적 방식이었다. 

- 하지만 state의 크기가 굉장히 커진다면 계산하는 것이 어려워질 것이다. 이러한 문제를 해결하기 위해서는 비동기적 방식의 알고리즘에 대해 알 필요가 있다.

## 2. 비동기적 Dynamic Programming

### 2.1 In-place DP

<center><img src="/assets/images/rl/inplace.jpg"  width="70%" ></center>
[<center>Source</center>](https://www.davidsilver.uk/wp-content/uploads/2020/03/)

- 비동기적 DP의 대표적인 방식으로 In-place 방식이 있다. In-place는 이전 value function으로 부터 현재의 value function을 update하는 동기적 방식과 다르게 현재까지 구해진 value function으로 부터 state를 거치면서 v(s)를 조금씩 update해 가는 방식이다. 때문에 memory 사용량을 절감하는 동시에 빠르게 수렴할 수 있다고 한다.

### 2.2 Prioitized Sweeping DP

<center><img src="/assets/images/rl/psdp.jpg"  width="70%" ></center>
[<center>Source</center>](https://www.davidsilver.uk/wp-content/uploads/2020/03/)

- 두번째는 prioitized sweeping 방식이다. 이 방법은 state에서 bellman 에러를 계산해서 가장 큰 state부터 먼저 value 값을 update해가는 방식이며 수렴속도가 빨라진다고 한다.

### 2.3 Real time DP

<center><img src="/assets/images/rl/rtdp.jpg"  width="70%" ></center>
[<center>Source</center>](https://www.davidsilver.uk/wp-content/uploads/2020/03/)

- 마지막으로 real time DP는 agent가 경험한 state를 기준으로 update하는 방식이다. 

## 3. DP의 한계

- 기본적으로 DP는 동기방식이든 비동기방식이든 모든 state들을 update하는 full-width backup구조이다. 이 때문에 state 수가 늘어날수록 비동기식 DP를 사용한다하더라도 계산과정이 기하급수적으로 많아진다는 문제가 발생한다.

- 또한 bellman equation에서 보았듯이 기본적으로 state transition probability를 알아야 DP update가 가능했다.

- 다음 post에서는 이러한 문제를 해결하기 위한 sampling 방식에 대해 알아볼 것이다.



## Reference
\[1]: [Reinforcement learning: an introduction](https://web.stanford.edu/class/psych209/Readings/SuttonBartoIPRLBook2ndEd.pdf)

\[2]: [Fundamental of Reinforcement Learning](https://dnddnjs.gitbooks.io/rl)

\[3]: [Fast Campus 강의자료](https://storage.googleapis.com/static.fastcampus.co.kr/prod/uploads/202008/153017-24/[%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4]-%EA%B5%90%EC%9C%A1%EA%B3%BC%EC%A0%95%EC%86%8C%EA%B0%9C%EC%84%9C-%EC%98%AC%EC%9D%B8%EC%9B%90-%ED%8C%A8%ED%82%A4%EC%A7%80---%EB%AA%A8%EB%8D%B8-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0%EC%9C%BC%EB%A1%9C-%EC%9D%B5%ED%9E%88%EB%8A%94-%EA%B0%95%ED%99%94%ED%95%99%EC%8A%B5-a-to-z.pdf)

\[4]: [Silver 교수님 강의자료](https://www.davidsilver.uk/wp-content/uploads/2020/03/)

