---
layout: post
title: Virtual Box Centos7 에서 Guest Addition 설치하기
---

※이 방법은 GUI 모드에서만 사용 가능합니다. command lines 모드에서는 [ssh로 접속하기](https://zenoengine.github.io/use-ssh-vbox-centos/)를 참고하셔서 보다 편한 환경을 구축할 수 있습니다.


Vritual Box 에서 Guest OS를 설치할 시 몇 가지 불편한 점들이 있습니다.(Host<->Guest로 복사-붙여넣기 라던가..)

그래서 Guest Addition을 설치해서 이 불편함들을 해소할 수 있습니다. (CentOS7을 기준으로 설명하겠습니다.)

### 선행 작업

우선 여러가지 개발도구를 사용할수 있게해주는 package를 설치해야합니다. 

```
//gcc, make, kernel-dvel 등
yum groupinstall "Development Tools" 
yum update
reboot
```

### Guest Addition 설치하기

Guest Addition CD를 삽입합니다.
```
장치-게스트 확장 CD삽입
``` 

그 다음으로는 xwindow 같은 gui 환경이 아니라면 mount라는 작업을 통해 cd-rom에 삽입된 cd를 

컴퓨터 안 폴더에 디렉토리로 연결 시켜줘야합니다. 명령어는 다음과 같습니다.

```
//cdrom 에 있는 내용들 모두(-r) /media 디렉토리에 연결
mount -r /dev/cdrom /media
```

이제 GuestAddition 설치하기를 실행합니다.

```
/media/VBoxLinuxAdditions.run
reboot
```


### Clipboard 사용

VirtualBox OS 설정 - 일반 - 고급 - 클립보드 공유 - 양방향

으로 설정하면 이제 복사 붙여넣기를 사용 할 수 있습니다.