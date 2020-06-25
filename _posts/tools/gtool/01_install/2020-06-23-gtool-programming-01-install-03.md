---
title: "Git blog 댓글기능 사용하기"
date: 2020-06-25
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



# 1. disqus 가입

### Github에서는 댓글기능을 제공하지 않기 때문에 우리는 disqus 서비스를 이용해서 댓글기능을 github 블로그에 적용해 볼 것이다.
- 먼저 [disqus 사이트](https://disqus.com) 에 접속하여 가입한다.
- 가입후 등장하는 'I want to install Disqus on my site' 버튼을 클릭한다.
- 사용할 disqus 이름을 설정해주고 Basic 버전으로 선택한다. (Basic은 무료버전이지만 유료버전과 큰 차이가 없다.)
- 이후 jekyll을 선택하고 Website URL에 본인의 github 주소를 적어준다.

# 2. 댓글 기능 적용

- 본인의 블로그 repository에서 _config.yml 파일에 접속한다.
- disqus_shortname에 가입시 설정한 이름을 다음과 같이 적어준다.
```h
disqus_shortname: 'disqus_name'
```
- 댓글 기능이 필요한 markdown post 파일에 들어가 처음 layout 설정 부분에 comments: True 로 적어준다. 
```h
---
title: "Git blog 댓글기능 사용하기"
date: 2020-06-25
category:
comments: true
---
```
- git add, commit, push 과정을 거쳐 본인의 홈페이지에 업로드 시키고 확인해 본다.


<br><br>
