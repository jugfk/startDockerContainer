# 젯슨나노에서 도커 컨테이너 시작하기

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

터미널에서 미리 만든 자바스크립트 flow.json 파일을 다운로드 하는법:
```
$ wget https://raw.githubusercontent.com/jetsonworld/javascript-thermal-monitor/master/flows.json
```
오른쪽에 ipmport를 클릭한후 다운로드한 flow.json을 업로드합니다.

![01image](https://raw.githubusercontent.com/jetsonworld/startDockerContainer/master/01_Images/01_Using_Node-RED_On_Docker.png)


