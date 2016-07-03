---
layout: post
title: VirtualBox CentOS7 SSH 사용 
---
<style>
.mbtablestyle {
        border-collapse: collapse;

}
td, th {
        border: 1px solid black;
        padding: 5px;
        }
</style>


우선 HostOS 의 IP를 확인합니다 (HostOS : Windows)

```
cmd ipcofnig
```

그리고 Guest OS 

 ```
 ip addr | grep inet
 ```

 필자의 경우 IP는 10.0.2.15/24 로 나왔습니다.

 이제 GuestOS를 종료하고 
 설정 - 네트워크 - 어댑터1 에서 고급을 눌러서 - 포트 포워딩 - 추가

| 이름 | 프로토콜 | 호스트IP | 호스트 포트 | 게스트 IP | 게스트 포트|
|---|---|---|---|---|---|
|  SSH | TCP  | [HOST IP] | [ANY PORT]  | 10.0.2.15.24   | 22 |
{:.mbtablestyle}

이제 SSH Program을 열어서 HOST IP 와, port : [AnyPORT] 입력하고 연결하면 SSH 연결이 됩니다.