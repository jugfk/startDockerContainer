# 젯슨 나노에서 도커 컨테이너 시작하기

* 도커 버전 확인하기
```
$ sudo docker version
```

* NVIDIA 컨테이너 런타임 확인하기
```
$ sudo docker info | grep nvidia
$ sudo dpkg --get-selections | grep nvidia
```

***

* 첫번째 <b>'헬로우 월드'</b> 실습하기
```
$ sudo docker run hello-world
$ sudo docker images
```

***

* 두번째 <b>‘도커 컨테이너 기반 노드레드’</b> 실습하기
```
$ sudo docker run -it -p 1880:1880 --name mynodered nodered/node-red
```
웹브라우져를 열어서 아래와같이
```
localhost:1880 
```
입력하세요.
![00image](https://raw.githubusercontent.com/jetsonworld/startDockerContainer/master/01_Images/00_Using_Node-RED_On_Docker.png)

먼저 다음과 같이 대쉬보드를 설치해주세요. 
![01image](https://raw.githubusercontent.com/jetsonworld/startDockerContainer/master/01_Images/01_Using_Node-RED_On_Docker.png)

![02image](https://raw.githubusercontent.com/jetsonworld/startDockerContainer/master/01_Images/02_Using_Node-RED_On_Docker.png)

터미널에서 미리 만든 자바스크립트 flow.json 파일을 다운로드 하는법:
```
$ wget https://raw.githubusercontent.com/jetsonworld/javascript-thermal-monitor/master/flows.json
```
오른쪽에 ipmport를 클릭한후 다운로드한 flow.json을 업로드합니다.

![03image](https://raw.githubusercontent.com/jetsonworld/startDockerContainer/master/01_Images/03_Using_Node-RED_On_Docker.png)

![04image](https://raw.githubusercontent.com/jetsonworld/startDockerContainer/master/01_Images/04_Using_Node-RED_On_Docker.png)

mynodered 컨테이너의 상태를 확인해봅니다.
```
sudo docker images
sudo docker ps
```

mynodered 컨테이너를 시작/정지하기

```
sudo docker start mynodered
sudo docker stop mynodere
```
노드레드의 디버깅 로그데이타 보기
```
sudo docker attach mynodered
```

***
* 세번째 <b>‘도커 컨테이너 기반 NGINX 웹서버’</b> 실습
```
$ mkdir example
$ cd example
$ wget https://raw.githubusercontent.com/jetsonworld/
$ sudo docker build --tag hello:0.1 .
$ sudo docker run --name hello-nginx -d -p 80:80 -v /root/data:/data hello:0.1
```

NGINX 웹서버 컨테이너의 상태확인하기
```
sudo docker images
sudo docker ps
```

NGINX 웹서버 컨테이너의 시작/정지하기
```
sudo docker start hello-nginx
sudo docker stop hello-nginx
```

(Thank you for your precious devotion.)
