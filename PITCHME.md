## Spring <span style="color:#99FF00">Security</span><br>
### **<span style="color:#00ff99">By 각자바스</span>**
---
|**Authentication**|**Authorization**|
|:-:|:-:|
|시스템 접근 시, 등록된 사용자인지 여부를 확인하는 것| 시스템 접근 후, 인증된 사용자에게 권한을 부여하는 것|
|시스템 로그인|권한에따른 접근 권한<br> 사용자 등급(일반/관리자)|

---
## **Why Spring Security?**
### 우리 시스템의 이슈
1. 시스템에 Authentication 만 존재
2. Login 과정의 로직 분리가 확실하게 되어있지 않다

---
### Solution
- Spring Security 활용
    - Role 기반의 접근 권한 지원
    - Spring MVC와의 분리

---
## **Adapt Spring Security (OAuth2)**

#### 1. Dependency 추가 붙이는 작업

```xml
<dependency>
    <groupId>org.springframework.security</groupId>
    <artifactId>spring-security-taglibs</artifactId>
    <version>SPRING_SECURITY_VERSION</version>
</dependency>

<dependency>
    <groupId>org.springframework.security.oauth</groupId>
    <artifactId>spring-security-oauth2</artifactId>
    <version>SPRING_SECURITY_OAUTH2_VERSION</version>
</dependency>
```
---
#### 2. Spring Security Filters
//필터들이 쫙 붙는 장면
---
#### 3. 인증 및 권한 제어 3가지 방법
<span style="float=left">1. @Secured</span> <br>

```java
@Secured("ROLE_USER")
@Secured("ROLE_ADMIN")
```

<span style="float=left">2. Configure in WebSecurityConfigurerAdapter</span> <br>

```java
@Override
protected void configure(HttpSecurity http) throws Exception {
    http
        .authorizeRequests()
        .antMatchers("/index").access("ROLE_ADMIN");
        .antMatchers("/**").access("ROLE_USER");
}
```

<span style="float=left">3. xml file</span> <br>

```xml
<intercept-url pattern="/index" access="hasRole('ADMIN')"/>
<intercept-url pattern="/**" access="hasRole('USER')" />
```

---
4. OAuth2를 이용하기 위한 방법으로 필터 확장 및 등록하는 법
- 다양한 리소스를 간편하게 등록해서 확장 가능
    - naver
    - facebook
    - 카카오
    - 등등..

---
5. 필터 동작 과정
---
6. Authorization 결과물
- 사진 2장
    - ROLE_USER 접근 불가.jpg + log
    - ROLE_ADMIN 접근 승인.jpg + log
---
## 시행착오

- Spring Security Boot에는 이렇게 되어 있었는데 Spring Security에서는 달랐다...

---
결론

- Spring MVC와 Spring Security의 완전한 로직 분리


---
## Q&A
#### 감사합니다.
