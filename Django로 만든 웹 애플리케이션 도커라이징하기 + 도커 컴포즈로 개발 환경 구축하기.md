# Pycon 2019 8/16 튜토리얼 1
> Django로 만든 웹 애플리케이션 도커라이징하기 + 도커 컴포즈로 개발 환경 구축하기  
[왜 굳이 도커를 사용해야하는가](https://www.44bits.io/ko/post/why-should-i-use-docker-container)
[도커란 무엇인가](https://gist.github.com/nacyot/eec41928ad9b9b2452e8695411f03f1c)
1. visual studio code 설치
2. Extenstions에서 remote-ssh 검색 후 설치
3. Settings에서 Dynamic Forwarding 활성화
4. [배포한 ip list](https://gist.github.com/raccoonyy/f05663850fce424b9fc292ab096b9c71)에서 ip를 찾기
5. ctrl + shift + p, '아이디@ip' 입력 후 비밀번호는 '@naver.com'(이메일 뒷부분)을 입력하여 접속
6. open folder 클릭 후, ok, 비밀번호 입력
7. 중앙 아래 terminal 클릭 후 '+'를 클릭하여 terminal을 추가
8. docker 설치
~~~
# 도커 설치 명령어
$ curl -s https://get.docker.com/ | sudo sh
$ sudo gpasswd -a <USERNAME> docker

# 도커 설치 확인
$ docker -v
$ docker info
~~~
- docker는 vm이 아닌 process
