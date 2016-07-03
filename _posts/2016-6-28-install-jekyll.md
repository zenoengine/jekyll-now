---
layout: post
title: Windows에서 Jekyll 설치하기
---


Markdown 이 잘되는 블로그 플랫폼을 찾다가. Jekyll을 발견하였습니다.

심플한 디자인이 마음에 들어서 사용해보려고 합니다.

Document를 보면 mac OS 기준으로 되있있지만, Windows에서 사용하는 방법에 대해 알아보고 

제가 겪은 절차에 대한 기록 포스팅을 입니다.


### Git Hub 에서 Fork

[Jekyll 저장소](https://github.com/barryclark/jekyll-now)를 가서 fork 버튼을 통해 제 저장소로 가져왔습니다!

README 파일에서 친절하게 설명을 해주고있습니다.


![Step 1](/images/step1.gif "Step 1")


1. fork를 뜨고

2. settings에서 저장소 이름을 [사용자 계정명].github.io 로 수정을 하면 바로 자신만의 블로그 페이지가 뜹니다!

### Push 전에 페이지를 확인하고 싶은데..

블로그를 local에서 Push전에 확인하는 방법에 대해서 찾다보니 좀 많이 설치해야 하더군요 ㅜ.ㅜ

차근차근 따라가봅니다.


### 본격적인 설치를 시작하자!

#### Ruby, Ruby Developer Kit
http://rubyinstaller.org/downloads/

※설치 시 Add Ruby Excutables to your PATH를 클릭해주세요.

cmd 창에서 편하게 사용하실 수 있습니다.

DevKit을 압축 폴더를 C:\RubyDK 로 가정하겠습니다.

```
//Ruby - DeveloperKit Binding
cd C:\RubyDK
ruby dk.rb init
ruby dk.rb install
```

#### Jekyll

Documentation에서 gem이 뭔가했는데 Ruby의 패키지 매니져더군요 (....)

jekyll을 설치해 줍니다.

```
gem install jekyll
gem install rouge // code blocks 기능 사용
```

#### Python

전 3.5.2버젼을 설치했습니다.

cmd에서 편리하게 사용하기 위해 환경 변수를 추가합니다.


```
setx path "%PATH%;[Python 설치 경로]"
setx path "%PATH%;[Python 설치 경로]\Scripts"

//예시
setx path "%PATH%;C:\Users\HongAhn\AppData\Local\Programs\Python\Python35-32"
setx path "%PATH%;C:\Users\HongAhn\AppData\Local\Programs\Python\Python35-32\Scripts"
```

환경 변수 설정을 한후 새로운 cmd창을 띄워서 잘 동작하는지 테스트 해봅니다.

```
python
pip
pip install Pygments // syntax highligthing 용
```

#### 마지막!

내 블로그 프로젝트를 컴퓨터에 clone 합니다.

```
cd c:\설치할 경로
git clone [jekyll fork clone path]
jekyll serve
``` 

이제 웹브라우져에서 127.0.0.1:4000 으로 접속하면 내 블로그가 뜹니다!!

해보고 나서 느낀점

장점 : 
마크 다운이 좋다!

단점 : 
포스팅별 이미지 파일을 따로 관리해야할거 같음..

템플릿에 적용기간이 필요

![_config.yml]({{ site.baseurl }}/images/config.png)