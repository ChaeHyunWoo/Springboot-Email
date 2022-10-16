# 스프링부트 이메일 전송 Test

### 1. 의존성
```gradle
dependencies {
    // 이메일 발송을 위해 의존성 추가
    implementation 'org.springframework.boot:spring-boot-starter-mail'
    implementation 'org.springframework.boot:spring-boot-starter-web'
    implementation 'org.springframework.boot:spring-boot-starter'
    compileOnly 'org.projectlombok:lombok'
    developmentOnly 'org.springframework.boot:spring-boot-devtools'
    annotationProcessor 'org.projectlombok:lombok'
    testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
```

### 2. EmailUtils.java 만들기
### 3. EmailController.java 만들기
### 4. application.properties 생성
```properties
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=구글 이메일 계정
spring.mail.password=구글 이메일 비밀번호
spring.mail.properties.mail.smtp.starttls.enable=true
spring.mail.properties.mail.smtp.starttls.required=true
spring.mail.properties.mail.smtp.auth=true
```
#### 4-1. application.yml 으로 작성할 경우
```yml
spring:
  mail:
    host: smtp.gmail.com
    port: 587
    username: 구글 이메일 계정
    password: 구글 이메일 비밀번호
    properties:
      mail:
        smtp:
          starttls:
            enable: true
            required: true
          auth: true
```
### 5. 구글 보안 수준이 낮은 앱의 엑세스
 - 주의할점은 2단계 인증이 되어있으면 안됨
 - Google계정관리 - 보안 - 앱 비밀번호 생성 - 생성된 비밀번호를 application 파일 password에 작성

### 6. 실행하기
http://localhost:8080/sendmail
