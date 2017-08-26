## Spring <span style="color:#99FF00">Security</span><br>
### **<span style="color:#00ff99">By 각자바스</span>**
---
|**Authentication**|**Authorization**|
|:-:|:-:|
|시스템 접근 시, 등록된 사용자인지 여부를 확인하는 것| 시스템 접근 후, 인증된 사용자에게 권한을 부여하는 것|
|시스템 로그인|권한에따라 사용 가능한 기능이 제한<br> 사용자 등급(일반/VIP/관리자)|

---
## **Why Spring Security?**
우리 시스템의 이슈
1. 우리의 시스템에서 Authentication은 없고 Authorization은 없다.
2. 로직 분리가 확실하게 되어있지 않다.

Security 부분을 추가하는데 있어서 Spring MVC 코드에 대한 수정 없이 기능을 추가 하고 싶다.

---
## **How to adapt Spring Security OAuth2**

3. Adapt Authorization
    - @RequestMapping("/admin/category")
    - WhiteList 식 Page 관리
- config.class에 url에 권한관련을 모아놓는 것이 아닌 어노테이션으로 컨트롤러에 권한을 표현하는 형태


---
결론

- Spring MVC와 Spring Security의 완전한 분리
- 


---
5. Q&A

