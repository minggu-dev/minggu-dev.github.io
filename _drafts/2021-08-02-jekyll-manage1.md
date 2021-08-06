---
layout: post
title:  "github 블로그 Jekyll 운영하기 - 테마 적용하기"
date:   2029-08-03 08:00:18 +0900
categories: Jekyll blog
tags: jekyll jekyll-theme
---
# Introduction

![jekyll이미지](/img/github-jekyll.png)
>
#### 이전에 Jekyll 블로그 생성법과 포스팅 방법까지 알아보았으니 이제 블로그를 꾸며주는 작업을 해보려고 한다.
#### 이번 글에서는 블로그의 테마를 적용시켜주는 과정을 알아보자.

# 테마 고르기
우선 [지킬 테마](http://jekyllthemes.org/) 사이트로 들어가 마음에 드는 테마를 골라준다. 내가 선호하는 테마는 심플한 디자인에 모바일에서 봐도 불편함이 없는지, 커스터마이징 하기에 편리해 보이는지를 보고 골라보았다.(취향에 따라 원하는 테마를 고르면 된다!)<br>

![스크린샷](/img/not-pure-poole.png)
> 내가 고른 테마는 [Not-Pure_Poole](https://github.com/vszhub/not-pure-poole)이라는 테마이다. 테마를 골랐으니 이제 내 블로그 폴더에 적용시켜 보자.

사실 처음 블로그를 생성하면 자동적으로 minima라는 테마가 적용된다. `bundle info minima`를 입력해 기본 테마의 정보를 알아볼 수 있다.(어쩐지 처음 블로그 생성했을 때도 나름 심플하고 이쁘게 구성되어있긴 했다.) 기존테마에서 내가 고른 테마로 바꾸기 위해 몇 가지 수정해 줘야 하는 사항들이 있다.

1. 'not-pure-poole' gem 설치
내 블로그 폴더 안에 있는 Gemfile에 `gem 'not-pure-poole'`을 추가하여 설치할 수 있도록 해준다.
2. 플러그인 추가
_config.yml에 다음을 추가한다.
```
plugins:
  - not-pure-poole
```


<br><br>
# 마무리
#### 오늘은 Jekyll디렉터리 구조에 대해 간단히 알아보고 무료 호스팅 지원을 받아 직접 포스팅까지 시도를 해보았다. 이제 겨우 블로그 운영이 가능한 단계까지 왔고 이후부터는 블로그 꾸며주는 방법과 포스트 작성법에 대해 좀 더 알아보고자 한다.


<br>
<br>
<br>
<br>
이제 막 알아가는 단계인 초보이므로 오류나 잘못된 점이 있다면 지적해주시면 감사합니다! 🥰
