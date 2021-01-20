# docker

TeamA project with docker

# docker로 프로젝트 실행하기

## 1. docker hub(아래 url)에 접속해서 client image 복사하기 (`docker pull anwlro7958/fuding:client`)

[dockerhub image](https://hub.docker.com/r/anwlro7958/fuding/tags?page=1&ordering=last_updated)

## 2. 프로젝트 폴더 터미널에서 붙여넣기 하고 엔터

## 3. 1번 url에 접속해서 server image 복사하기 (`docker pull anwlro7958/fuding:server`)

## 4. client와 server를 포함하는 루트폴더에 docker-compose.yml 파일을 위치 시키기

## 5. 루트 폴더 터미널에서 `docker-compose up` 입력

##### node-sass binding 관련 에러가 날 경우

1. `docker ps` 입력 후 client 컨테이너 ID 복사 <br>
2. `docker exec -it 컨테이너ID bash` 터미널에 입력하면 컨테이너에 접속됨 <br>
3. 컨테이너에 접속 후 app폴더 아래에서 `npm uninstall node-sass` 입력 <br>
4. `npm install node-sass@4.14.1` 입력 <br>
5. exit로 컨테이너 나온 후 다시 `docker-compose up`하면 정상 작동 됨!
