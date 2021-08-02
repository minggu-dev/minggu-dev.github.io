---
layout: post
title:  "github 블로그 Jekyll 시작하기(2) - 블로그 생성"
date:   2021-07-28 16:10:18 +0900
categories: Jekyll blog
---
## **Introduction**

![jekyll이미지](/img/github-jekyll.png)
>
#### 지난 글에서 Jekyll에 대해 간단히 알아보았다. 이번 글에서는 Jekyll 설치하는 방법과 블로그를 만들어보기까지 해볼 것이다.

<br>
<br>
## **Jekyll 설치하기**

### 1. 루비(Ruby) 설치
Jekyll은 Ruby로 작성되어있기 때문에 우선 Ruby를 설치해 주어야 한다.<br>
(참고로 Ruby를 잘 모른다 해도 상관 없다! Ruby는 그저 Jekyll을 설치하고 Jekyll 서버를 컴퓨터에서 실행시켜주기 위한 것이기 때문에 설치하고 서버를 실행시켜주는 방법만 알면 된다.)

[루비 다운로드](https://rubyinstaller.org/downloads/archives/)
![루비 다운로드 사이트](/img/ruby-install01.png)
> 나는 Ruby+Devkit 2.5.5-1 (x64)버전을 다운로드 받았다.

이 사이트로 들어가 Ruby를 다운로드 하면 된다. 지킬 공식 사이트에서 보면 **Ruby버전은 최소 2.4 이상**을 요구하고 있기 때문에 그 이상의 버전으로 설치하는 것을 추천한다.

Ruby 버전을 확인하기 위해선 명령프롬포트를 켜고 다음 명령어를 쳐서 확인할 수 있다.

`ruby -v`

![루비 버전 확인](/img/ruby-install02.png)
> 제대로 설치된 것을 확인!

<br><br>

### 2. 지킬(Jekyll) 설치
Ruby를 설치 했으니 이제 Jekyll을 설치해 보자. 먼저 Ruby 명령어 프롬포트를 실행시켜보자
![루비 명령어 프롬포트](/img/ruby-install03.png)
> 간단하게 rub까지만 쳐도 나온다.

Ruby 명령 프롬포트를 실행시켰다면 이제 본격적으로 Jekyll을 설치해 보자.

`gem install jekyll`

위의 명령어를 치면 Jekyll을 설치하기 시작한다. 여기서 gem이 무엇인지 간단히 알아보자면 Ruby에서 gem은 패키지라고 보면 되고 필요한 기능이 있다면 추가해서 사용할 수 있다. Jekyll도 그러한 gem 중 하나이다.

지킬 설치가 완료했다면 이제 지킬 블로그를 운영하기 위해 로컬저장소에 블로그를 생성해 줄것이다.
원하는 디렉토리로 cd 명령어를 통해 이동한 후 아래의 명령어를 실행한다.

`jekyll new 블로그이름`

이제 블로그이름으로 새로 폴더가 생긴 것을 볼 수 있을 것이다.<br>새로생긴 폴더 안으로 들어가 추가적으로 gem을 설치해 줘야 하는데 폴더 안에 보면 Gemfile이라는 파일 하나가 생성된 것을 볼 수 있다. Gemfile 안에 설치해줘야할 gem들이 등록이 되어있고 Gemfile에 등록된 gem들의 의존성을 파악해 설치하도록 도와주는 **Bundler**가 있다. 먼저 Bundler를 설치해보자!

`gem install bundler`

Bundler 설치가 완료되었다면 다음의 명령어를 통해 Gemfile에 등록된 gem들을 설치해 준다.

`bundle install`

설치가 완료되었다면 다음의 명령어를 통해 웹사이트를 서버에 올려준다.

`bundle exec jekyll serve`

>
>만약 위의 명령어를 쳤을 때 인코딩 에러가 발생한다면
>
>`chcp 65001`
>
>이 명령어를 통해 인코딩을 utf-8로 맞춰주고 다시 해보자

그리고 http://127.0.0.1:4000 으로 접속을 하면..


![지킬 초기 블로그](/img/jekyll01.png)
> 초기 블로그 홈 화면

이로써 Jekyll 초기 블로그 생성을 마치게 되었다.



<br>
<br>

## **마무리**
#### 오늘은 Jekyll을 설치하고 직접 블로그를 생성하는 과정을 다뤄보았다. 설치 과정을 보면서 Ruby를 다운받길래 새로운 언어를 공부해야하나 싶었지만 정말 기초적인 Ruby에 대해서만 알고 넘어가도 될 정도로 Ruby를 통해 할게 많이 없었고 차근차근 따라가다보니 쉽게 블로그 생성까지 마무리 할 수 있었다.

#### 다음 글에선 Jekyll 포스팅 하는 방법과 Markdown 작성법에 대해 알아보겠다.


<br>
<br>
<br>
<br>
이제 막 알아가는 단계인 초보이므로 오류나 잘못된 점이 있다면 지적해주시면 감사합니다! 🥰
