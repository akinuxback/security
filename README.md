# security - OAuth2.0

### pom.xml - security, Oauth2, 시큐리티 thymeleaf 적용
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-security</artifactId>
</dependency>
<dependency>
    <groupId>org.thymeleaf.extras</groupId>
    <artifactId>thymeleaf-extras-springsecurity5</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-oauth2-client</artifactId>
</dependency>
```

### db는 oracle 로 하였다.
```oracle
CREATE USER security IDENTIFIED BY security

DEFAULT tablespace USERS

TEMPORARY tablespace TEMP;


GRANT RESOURCE, CONNECT TO security;
```

### 오라클 외부 라이브러리 추가 pom.xml
```oracle
<!-- 오라클 외부라이브러리 추가 -->
<dependency>
    <groupId>orai18n</groupId>
    <artifactId>orai18n</artifactId>
    <version>1.0</version>
    <scope>system</scope>
    <systemPath>${project.basedir}/src/main/resources/libs/orai18n.jar</systemPath>
</dependency>
```

### application.yml
```oracle
spring:
datasource:
    url: jdbc:oracle:thin:@localhost:1521/orcl
    username: security
    password: security
    #    driver-class-name: oracle.jdbc.driver.OracleDriver - 9버전 이후로 이름 변경됨
    driver-class-name: oracle.jdbc.OracleDriver
jpa:
    hibernate:
      ddl-auto: create
    properties:
      hibernate:
        # show_sql: true
        format_sql: true
```


