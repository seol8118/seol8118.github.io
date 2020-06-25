---
title: "Git 설치및 blog 개설하기"
date: 2020-06-23
category:
  - gtool
tag :
  -
sidebar:
  nav: sidebar-gtool
mathjax: "true"
author_profile: false
toc: true
toc_label: "Contents"
toc_icon: "cog"
toc_sticky: true
header:
  overlay_image: /assets/images/r.jpg
  overlay_filter: 0.5
comments: true
---

> Tools > Git > Git blog

#### * 본 글은 Git, Ruby, VScode 를 한 번도 사용해보지 않은 사람을 대상으로 쓰여졌습니다.  


# 1. Git hub 가입

### Git blog 를 개설하기 위해 우선 [Git hub 홈페이지](https://github.com/join) 에서 가입을 하자.

# 2. 블로그 구축을 위한 프로그램 다운로드
### Git hub에 가입을 완료했다면 블로그 구축을 위한 다음 프로그램을 다운로드하자.

## 1.1 다운로드 주소 (Window)

- [Ruby 다운로드](https://rubyinstaller.org/downloads/)
- [Git](https://git-scm.com/download/win)
- [VScode 다운로드](https://code.visualstudio.com/docs/?dv=win) 


# 3. 블로그 repository 만들기

- Git hub에 접속하여 repository name을 (자신의 ID).github.io 로 해서 만든다.
- (자신의 ID)/(자신의 ID).github.io 가 앞으로 사용할 blog의 도메인이 된다.

# 4. 원하는 Jekyll theme 고르기
- 자신이 원하는 블로그 테마를 스스로 만들어도 되지만 Jekyll이라는 툴은 이미 어느정도 정형화된 홈페이지 테마를 제공한다. 
- 따라서 우리는 Jekyll theme을 이용하여 블로그를 만든뒤 그것을 customizing 하는 방법을 알아볼 것이다.
- [Jekyll theme](http://jekyllthemes.org/) 홈페이지에서 원하는 테마를 다운로드 한다.
- 압축은 본인이 원하는 곳에 풀어도 되지만 지금은 Git blog 사용이 처음이라면 C://(본인ID).github.io 에 압축을 푼다.

# 5. Jekyll theme을 본인 git hub에 업로드 하기
- 다운 받은 jekyll theme을 직접 홈페이지에 접속해서 업로드 해도 되지만 나중에 블로그 관리할 때마다 홈페이지에서 업로드하긴 번거롭기 때문에 앞서 받은 Git 프로그램을 사용할 것이다.

- Git bash 프로그램을 이용해서 다운받은 jekyll 경로로 이동한다.
- 다음과 같은 코드를 입력하여 자신의 github repository에 업로드한다.

```bash
$ git init
$ git add .
$ git commit -m "Initial commit"
$ git remote add origin "https://github.com/ID/ID.github.io"
$ git push origin master
```
- 몇 분후 "https://github.com/ID/ID.github.io" 주소에 접속하여 자신의 테마가 제대로 나오는지 확인한다.



**주의 사항**

- 각각의 설치 파일이 위치한 경로에 한글이 포함되어 있으면 설치 과정에 문제가 발생할 수 있다.

<br><br>
