# SpringSecurity


### 스프링 시큐리티란?
스프링 시큐리티는 스프링 기반의 애플리케이션에서 보안을 위해 **인증**(Authentication)과 **권한 부여**(Authorization)를 사용하여 접근을 제어하는 **프레임워크**

### 스프링 시큐리티가 필요한 이유
Spring Security는 보안과 관련해서 체계적으로 많은 옵션을 제공해주기 때문에 개발자 입장에서는 일일이 보안 관련 로직을 작성하지 않아도 된다는 장점이 있음

### 인증과 인가
인증(Authentication)은 자원을 요청하는 사용자를 식별하는 것
권한(Authorization)은 인증절차가 끝난 접근 주체가 보호된 리소스에 접근 가능한지 결정하는 것

### 스프링 시큐리티 인증 처리 과정

### 스프링 시큐리티 인가 처리 과정






* * *
1. XSS
> 크로스 사이트 스크립팅(Cross-Site Scripting, XSS)은 사용자의 입력값에 의해 자신 혹은 타인의 브라우저에 스크립트를 삽입하여 사용자를 공격하는 기법 
> 사용자의 입력값이 즉시 나타나는 비 지속적인 유형(Non-persistent)과 사용자의 입력이 데이터베이스(혹은 파일, 브라우저 리소스 등)에 저장되어 지속적(Persistent)으로 발생하는 유형이 있다.
> 대응방안으로는 HTML Escape / XSS 필터 사용 / Security Response Header 사용 / 적절한 Content-Type Header 사용 / 쿠키속성 HTTP Only 사용 등이 있다.
2. SQLi
> SQL injection은 입력값에 의해 공격자가 원하는 쿼리를 실행하는 공격이다. 
```
public List<Tutorial> getTutorialList(TutorialSearchCondition tutorialSearchCondition) {
  String getTutorialByNameQuery = "SELECT * FROM TUTORIAL WHERE name = '" + tutorialSearchCondition.getName();
  Query query = entityManager.createNativeQuery(getTutorialByNameQuery, Tutorial.class);
  
  List<Tutorial> tutorialList = query.getResultList();
  return tutorialList;
}
```
> 입력값을 통해 쿼리가 변조가능하면 공격자가 원하는대로 쿼리가 생성할 수 있게 된다.
> SELECT * FROM TUTORIAL WHERE NAME = '1' = '1'등
> 대응방안으로는 1. 쿼리를 정적으로 만들기가 있고 2. 동적으로 만들어야하는경우 입력값이 아닌 정해진 값을 사용하도록 처리하면 된다.


4. Business Logic Vlunerability
5. CSRF
6. Open Redirection
7. API 보안 버그
8. SSRF
9. Open Source 관리 미흡

문제 정의 및 해결법 정리
+ SpringBootDev.com -> Spring Security 내용 정리
+ Spring Security 3/e 책 정리
