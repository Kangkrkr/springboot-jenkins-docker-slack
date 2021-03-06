# springboot-jenkins-docker-slack

# Docker 명령어로 Jenkins 설치
- 도커 이미지 및 컨테이너 간략 제어 명렁어
>https://brunch.co.kr/@hopeless/10
- 아래의 명령어를 입력하여 도커에서 젠킨스 이미지를 내려받는다.
```aidl
docker pull jenkins/jenkins:lts
```

- 이미지를 모두 내려받은 경우, 아래의 명령어를 입력하여 컨테이너에 올리는 작업을 수행한다.
```aidl
// 8181 포트로 클라이언트에서 접속할 수 있다. 
<이전버전> docker run -d -p 8181:8080 -v /jenkins:/var/jenkins_home --name [사용할 컨테이너명] -u root [이미지명]
<신규버전> sudo docker run -d -p 8181:8080 -v /jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock -u root [젠킨스이미지ID]
-d	detached mode 흔히 말하는 백그라운드 모드
-p	호스트와 컨테이너의 포트를 연결 (포워딩)
-v	호스트와 컨테이너의 디렉토리를 연결 (마운트)
–name	컨테이너 이름 설정
-u 실행할 사용자 지정
```
- 이후, 브라우저에서 8181 포트로 접속 후, 아래 명령어를 입력하여 admin 계정의 암호를 확인한다. 
```
docker logs [젠킨스 컨테이너명]
```
- 설치화면에서 나오는 버튼 중 Install suggested pluings를 선택하여 설치한다.
- 젠킨스 컨테이너의 터미널로 접속하고자 할 경우 아래 명령어를 입력한다.
```aidl
docker exec -it [컨테이너명] /bin/bash
```
#GitHub 와 Jenkins 연동
- Github 프로젝트에 WebHook 추가 및 build pipeline 등록
> https://wickso.me/jenkins/continuous-integration/
# Jenkins를 Graceful-Shutdown 시키기
- https://it00.tistory.com/40

