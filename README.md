# Global crowdfunding project with docker

글로벌하게 프로젝트를 펀딩하는 Web Application 입니다. <br>
사용자의 나라에 맞게 제품을 소개하는 레이아웃과 제품을 등록하는 레이아웃을 다르게 보여줍니다. <br>
기존 펀딩 사이트와는 다르게 프로젝트를 펀딩한다는 점에서도 차별을 두었습니다.

# docker로 프로젝트 실행하기

#### 1. docker-compose.yml이 있는 곳에서 `docker-compose build` 입력 후 엔터 
![ELK-docker-compose build](https://user-images.githubusercontent.com/67114268/106850304-9bb1ad00-66f7-11eb-97b0-99f4ee078d3b.gif)


#### 2.`docker-compose up` 입력 후 엔터
![ELK-docker-compose up](https://user-images.githubusercontent.com/67114268/106850306-9eac9d80-66f7-11eb-8c7a-c268e0ebcf32.gif)


## node-sass binding 관련 에러가 날 경우

1. `docker ps` 입력 후 client 컨테이너 ID 복사 <br>
2. `docker exec -it 컨테이너ID bash` 터미널에 입력해서 컨테이너에 접속 <br>
3. 컨테이너에 접속 후 app폴더 아래에서 `npm uninstall node-sass` 입력 <br>
4. `npm install node-sass@4.14.1` 입력 <br>
5. exit로 컨테이너 나온 후 다시 `docker-compose up`하면 정상 작동
