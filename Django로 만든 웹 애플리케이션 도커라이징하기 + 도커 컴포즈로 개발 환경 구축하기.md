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
- [docker build](file:///C:/Users/m_i_n/Downloads/From%20Dockerizing%20to%20Docker%20Compose.pdf)
- <strong>볼륨을 마운트</strong>


# Pycon 2019 8/16 튜토리얼 2
> Deep learning & Music
1. 소리 인식 - Sampling, Quantizing, Encoding
1.1 음악 데이터 ~ 2.2kHz
2. 주피터 노트북 설치 - 헉! 안된다.. 넘 오래 걸려..
3. 이산푸리에변환을 시도하면 시간영역이 날아가기 때문에 shot time fourier transform을 이용함
 - 단위를 1초 등등을 이용
 - time domain에서 구간을 설정하여 인식하도록 함!
 - FFT에서 불연속적인 구간을 막기 위해 window function을 곱해준다 (기본적으로 4가지, 보통 hann 파형을 많이 이용)
 - 분석을 1/2, 1/4정도 겹치게 나누어 분석
 - 주파수를 조작하여 임의로 음을 나게 할 수도 있음 (소리를 모델링하는 과정에서 설정할 수 있다는 예시)
 - 딥러닝에서 사용하는 샘플링 방법은 STFT !
 - 윈도우 사이즈에 따라 time domain과 frequency domain이 trade-off된다 - 고려해야하는 부분
 - 멜스펙토그램(mfcc) / 사람들이 저주파에 대한 것은 크게 느끼고 인접한 주파수의 구분을 잘 하지 못하기 때문에 높은 주파수에는 멜 간격을 크게 한다
4. Music classification
 - row wave form 좋은 효율을 내고 있음!
 - 1-D CNN(frequency고정, time기준으로 곱해진다 - 빠르게 학습, small data set에서 잘 적용)
 - 2-D CNN(주로 이미지 다룸, frequency와 time이 모두 가변적으로 변해짐 - 보다 큰 data set에 잘 적용)
 - sample CNN
 [강의 자료](http://localhost:8889/notebooks/Anaconda3/PYCON%20Tutorial.ipynb)
 
 - 음성 / 음악이 굉장히 비슷한 커널이라 테이터 셋만 바꿔보면 적용해볼 수 있음!
- freesound audio tag?
