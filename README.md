# Pudding (Docker)

Global Project Funding Service

글로벌하게 프로젝트를 펀딩 서비스를 제공하는 Web Application 입니다. <br>
나라마다 제품 설명 방식과 인기있는(잘 팔리는) 제품이 다르기 때문에 이에 착안해 하나의 상품에 대해 여러 개의 설명 레이아웃을 제공하도록 하였습니다. 사용자가 브라우저에 설정한 기본언어를 인식해 사용자가 제품 디테일 페이지에 들어가면 그 나라에 맞는 제품 소개 레이아웃을 보여주도록 하였습니다. 만약 해당 나라에 맞는 설명이 등록되어 있지 않는 경우, 사이트의 default 언어인 영어 버전에 레이아웃을 보여주도록 구현하였습니다. <br>

[사용기술 스택](https://github.com/siliconValleyTeamA/client/wiki/Design-Doc#%EC%82%AC%EC%9A%A9%EA%B8%B0%EC%88%A0) <br>
[ERD](https://github.com/siliconValleyTeamA/client/wiki/Schema)

## ✋Team Members

- [![title](https://img.shields.io/badge/DEVLOPER-최윤선-123456)](https://github.com/OMEGA-Y)
- [![title](https://img.shields.io/badge/DEVLOPER-이연정-123456)](https://github.com/YeonJeongLee00)
- [![title](https://img.shields.io/badge/DEVLOPER-유창헌-123456)](https://github.com/dbckdgjs369)
- [![title](https://img.shields.io/badge/DEVLOPER-노기진-123456)](https://github.com/nohgijin)

---

## 🐳Quick Start 

# Start project with docker

### 1. Clone Packages
```bash

git clone https://github.com/siliconValleyTeamA/docker.git

```

### 2. `docker-compose build` where docker-compose.yml is placed
![build](https://user-images.githubusercontent.com/67114268/106907141-43070200-6741-11eb-99b4-93f812b19aeb.gif)

### 3. `docker-compose up`

![compose up](https://user-images.githubusercontent.com/49175629/106901338-f91b1d80-673a-11eb-9e72-5e47cf9dd1a7.gif)

---

## About node-sass binding error

1. `docker ps` 입력 후 client 컨테이너 ID 복사 <br>
2. `docker exec -it 컨테이너ID bash` 터미널에 입력해서 컨테이너에 접속 <br>
3. 컨테이너에 접속 후 app폴더 아래에서 `npm uninstall node-sass` 입력 <br>
4. `npm install node-sass@4.14.1` 입력 <br>
5. exit로 컨테이너 나온 후 다시 `docker-compose up`하면 정상 작동

---

## Container
- ![title](https://img.shields.io/badge/-React-61DAFB?&logo=React&logoColor=white)
- ![title](https://img.shields.io/badge/-Node.js-339933?&logo=Node.js&logoColor=white)  ![title](https://img.shields.io/badge/-Express-000000?&logo=Express&logoColor=white) 
- ![title](https://img.shields.io/badge/-Elasticsearch-F4BD19?&logo=Elasticsearch&logoColor=white)
- ![title](https://img.shields.io/badge/-Logstash-02BFB3?&logo=Logstash&logoColor=white)
- ![title](https://img.shields.io/badge/-Kibana-E9488C?&logo=Kibana&logoColor=white)
- ![title](https://img.shields.io/badge/-MySQL-4479A1?&logo=MySQL&logoColor=white)

--> 📁 Client : https://github.com/siliconValleyTeamA/client   
--> 📁 Server : https://github.com/siliconValleyTeamA/server <br>
--> 📁 ELK(Elasticsearch+Logstash+Kibana) : https://github.com/siliconValleyTeamA/ELK

---

## ELK Details

Based on the Docker images:

* Elasticsearch : docker.elastic.co/elasticsearch/elasticsearch:7.10.2
* Logstash(**arm64 version**) : docker.elastic.co/logstash/logstash:8.0.0-SNAPSHOT-arm64
* Logstash(**basic version**) : docker.elastic.co/logstash/logstash:7.10.2
* Kibana : docker.elastic.co/kibana/kibana:7.10.2
* MySql : mariadb:10.5.8-focal

By default, the stack exposes the following ports:

* 5001: Logstash TCP input
* 9200: Elasticsearch HTTP
* 9300: Elasticsearch TCP transport
* 5601: Kibana
* 3306: MySql

**If your architecture is not arm64, change the Dockerfile image of logstash to basic version.**

---

## Project Structure
```bash
|-- docker
      |
      |
      |--client 
      |    |..//(siliconValleyTeamA/client에서 clone한 폴더)
      |
      |--server
      |  ..//(siliconValleyTeamA/server에서 clone한 폴더)
      |
      |--elasticsearch
      |       |  ..// elasticsearch 관련 파일
      |       |
      |       |--Dockerfile
      |       |
      |       |--config
      |            |
      |            |--elasticsearch.yml
      |
      |--kibana
      |       |  ..//kibana 관련 파일
      |       |
      |       |--Dockerfile
      |       |
      |       |--config
      |            |
      |            |--kibana.yml
      |
      |--logstash
      |       |..//logstash 관련 파일
      |       |
      |       |--Dockerfile
      |       |
      |       |--mysql-connector-java-5.1.49.bin.jar //jdbc 연결을 위한 파일
      |       |
      |       |-- config
      |       |     |
      |       |     |--logstash.yml
      |       |     |
      |       |     |--pipeline.yml
      |       |      
      |       |--pipeline
      |       |      |
      |       |      |--logstash.conf // db에서 받는 input과 elasticsearch에 저장되는 output을 
      |       |
      |
      |--docker-compose.yml
      |  ..// 도커 설정파일
      |
      |
 ```
      

