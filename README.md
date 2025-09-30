# EurekaClient

## 소개

이 프로젝트는 Spring Boot 기반의 Eureka Client 예제입니다. Netflix Eureka 서버에 등록되어 서비스 디스커버리 기능을 활용할 수 있습니다.

## 주요 기능

-   Eureka 서버에 클라이언트로 등록
-   RESTful API 제공
-   Sleuth, Zipkin을 통한 분산 트레이싱 지원
-   Actuator를 통한 모니터링 지원

## 환경 설정

-   Java 1.8 이상
-   Maven
-   Spring Boot 2.1.2
-   Spring Cloud Greenwich

## 실행 방법

1. Eureka 서버가 실행 중인지 확인하세요 (기본 주소: http://localhost:8761).
2. 아래 명령어로 애플리케이션을 실행합니다.

    ```bash
    ./mvnw spring-boot:run
    ```

3. 애플리케이션이 8081 포트에서 실행됩니다.

## 주요 설정 (application.yml)

```yaml
server:
	port: 8081
spring:
	application:
		name: eureka-client
eureka:
	client:
		serviceUrl:
			defaultZone: http://localhost:8761/eureka/
```

## 제공 API 예시

-   `/client/get-map-data` : 간단한 Map 데이터 반환
-   `/client/test` : 테스트용 데이터 반환
-   `/client/long-time` : 랜덤 대기 후 데이터 반환

## 예시 응답

```json
{
    "code": "100200",
    "msg": "success",
    "data": "this is eureka client. 12345"
}
```

## 참고

-   [Spring Cloud Eureka 공식 문서](https://cloud.spring.io/spring-cloud-netflix/multi/multi_spring-cloud-eureka-server.html)
