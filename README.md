# Pudding (docker)

Global Project Funding Service

글로벌하게 프로젝트를 펀딩하는 Web Application 입니다. <br>
사용자의 나라에 맞게 제품을 소개하는 레이아웃과 제품을 등록하는 레이아웃을 다르게 보여줍니다. <br>
기존 펀딩 사이트와는 다르게 프로젝트를 펀딩한다는 점에서도 차별을 두었습니다.

## ✋Team Members

- [![title](https://img.shields.io/badge/DEVLOPER-최윤선-123456)](https://github.com/OMEGA-Y)
- [![title](https://img.shields.io/badge/DEVLOPER-이연정-123456)](https://github.com/YeonJeongLee00)
- [![title](https://img.shields.io/badge/DEVLOPER-유창헌-123456)](https://github.com/dbckdgjs369)
- [![title](https://img.shields.io/badge/DEVLOPER-노기진-123456)](https://github.com/nohgijin)

---

## 🐳Quick Start 

# docker로 프로젝트 실행하기

### 1. Clone Packages
```bash

git clone https://github.com/siliconValleyTeamA/docker.git

```

### 2. `docker-compose build` where docker-compose.yml is placed
```bash

docker-compose build

```

### 3. `docker-compose up`
```bash

docker-compose up

```
---

## node-sass binding 관련 에러가 날 경우

1. `docker ps` 입력 후 client 컨테이너 ID 복사 <br>
2. `docker exec -it 컨테이너ID bash` 터미널에 입력해서 컨테이너에 접속 <br>
3. 컨테이너에 접속 후 app폴더 아래에서 `npm uninstall node-sass` 입력 <br>
4. `npm install node-sass@4.14.1` 입력 <br>
5. exit로 컨테이너 나온 후 다시 `docker-compose up`하면 정상 작동

---
## 프로젝트 구조
```bash
|-- docker
      |
      |
      |--client 
      |  ..//(siliconValleyTeamA/client에서 clone한 폴더)
      |
      |--server
      |  ..//(siliconValleyTeamA/server에서 clone한 폴더)
      |
      |--elasticsearch
      |  ..// elasticsearch
      |
      |--kibana
      |  ..//kibana
      |
      |--logstash
      |  ..//logstash
      |
      |--docker-compose.yml
      |  ..// 도커 설정파일
      |
      |
 ```
      

