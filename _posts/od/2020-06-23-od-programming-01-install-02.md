---
title: "Git blog 글쓰기"
date: 2020-06-23
category:
  - object detection
tag :
  - object detection
sidebar:
  nav: sidebar-od
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



# 1. Git blog를 새글 작성

### Git blog를 개설했다면 이제 새로운 글을 작성하고 업로드 시켜보자.
- 앞서 설치한 VScode를 실행하여 c://{ID}.github.io 폴더를 불러온다.
- VScode는 code 편집기로 글을 markdown 으로 작성하고 그에 대한 실행화면을 바로 볼 수 있는 장점이 있다.
- _posts 폴더에 글을 작성하게 되면 새 글을 업로드 할 수 있다.
- _posts/ 폴더에 YYYY-MM-DD-{제목}.md 이름으로 파일을 만들고 markdown 으로 글을 작성한다.

# 2. 새글 업로드

- 저장한 뒤 바로 git bash를 사용하여 업로드하고 확인해도 되지만 실제 git hub 홈페이지에 반영되는데에는 시간이 소요되기 때문에 블로그 수정 및 관리가 어렵다. 따라서 우리는 로컬에서 서버를 만들어 수정된 것을 미리 확인하고 실제 서버로 업로해 줄 것이다.
- 이전에 설치한 Ruby prompt를 실행한뒤 jekyll 과 bundler 패키지를 설치해준다.
```R
>gem install jekyll bundler
```
- 이후 자신의 github 폴더로 들어가서 bundle 명령어를 통해 필요한 패키지를 설치해주고 로컬 서버를 실행시켜준다.
```R
>bundle
>bundle exec jekyll serve 
```
- 그럼 로컬 서버에 대한 주소가 반환되고 인터넷 창에서 접속하면 로컬에서 자신의 블로그를 실행할 수 있게 된다.
- 이후 에디터로 수정을 하면 바로 로컬서버에 반영되어 확인할 수 있으며 최종 확인을 마친뒤에 git hub에 업로드를 하면 된다. 

<br><br>
