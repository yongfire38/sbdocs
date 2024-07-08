# Spring Boot Reference Documentation Assistant

This is a little demo I put together to show off the features of [Spring AI](https://spring.io/projects/spring-ai). This
is a command line utility that utilizes Open AI. To augment GPT-4 I am using a technique called Retrieval Augmented Generation (RAG)
to provide up to date information about Spring Boot using the Spring Boot Reference documentation. If you want to see
how I built this application you can check out the video below. 

[YouTube Tutorial](https://youtu.be/ZoPVGrB8iHU)

## Dependencies 

- Web 
- Shell
- JDBC API
- Open AI
  - spring-ai-pdf-document-reader (not available in the Spring Initializr)
- PgVector
- Docker Compose 
- GraalVM Native Support

[Spring Initiliazr](https://start.spring.io/#!type=maven-project&language=java&platformVersion=3.2.5&packaging=jar&jvmVersion=21&groupId=dev.danvega&artifactId=aidocs&name=aidocs&description=Demo%20project%20for%20Spring%20Boot&packageName=dev.danvega.aidocs&dependencies=web,spring-shell,jdbc,spring-ai-openai,spring-ai-vectordb-pgvector,docker-compose,native)

## 사전 준비

- jdk-21.0.2 사용
- docker desktop 설치, openAI api key 설정 필요

## DB 확인

```
// Postgre DB 컨테이너 붙기
docker exec -it sbdocs-pgvector-1 bin/bash

//psql 실행
psql --username admin --dbname sbdocs

//db 목록 확인
\l

//sbdocs DB에 connect
\c sbdocs

//테이블 목록 확인
\dt
```

## shell 실행
```
//예시와 같이 질의하면 된다
q "@RestControllerAdvice를 사용한 예제 코드를 알려주세요"
```