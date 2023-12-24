## Thymeleaf

```
화면을 동적으로 만들어주는 서버 사이드 템플릿 엔진인 Thymeleaf를 사용하여서 개발하였습니다.
Thymeleaf의 확장명은 .html이며, 문법은 html 태그 안쪽에 속성으로 사용됩니다.
Thymeleaf는 스프링에서 권장하는 서버 사이드 템플릿 엔진입니다. 이것 외에도 jsp, freemarker, groovy, mustache 등이 있습니다.
```
#### Thymeleaf 예제용 컨트롤러 작성
![image](https://github.com/mr-won/Shopping_Mall/assets/58906858/6aee43b1-3c08-4b1b-aa74-4f824629ce25)
```
url의 /thymeleaf 경로로 오는 요청을 처리하기 위해 RequestMapping 어노테이션을 ThymleafExController에 줘서
ThymeleafExController가 처리하도록 합니다.

/thymeleaf 경로 뒤에오는 /ex01 경로로 오는 요청은 thymeleafExample01 메소드가 처리하도록 하고 이 메소드에서
모델 객체를 이용해서 뷰에 전달한 데이터를 key, value 구조로 넣어줍니다.(model.addAttribute(key,value)
```
#### 서버용 Thymeleaf html 파일 작성
![image](https://github.com/mr-won/Shopping_Mall/assets/58906858/cef2f76f-84ff-4569-a30d-5dd4ab9b526b)
```
컨트롤러에서 추가한 키의 데이터를 화면에 출력하도록 <body> 태그 안에 th:text=${key} 값의 형태로 넣어줍니다.
Controller에서 넘겨준 데이터가 화면에 출력되는 것을 알 수 있습니다.
```
#### ShopApplication 실행결과
![image](https://github.com/mr-won/Shopping_Mall/assets/58906858/dc763957-1698-4a80-9127-93740faab1e3)

## Spring Boot Devtools
```
Spring Boot Devetools는 애플리케이션 개발 시 생산성을 향상시킬 수 있는 유용한 기능들을 제공합니다.
그 중 세 가지(Automatic Restart, Live Reload, Property Defaults)를 활성화해보겠습니다.
```
#### Automatic Restart 적용하기
#### pom.xml
![image](https://github.com/mr-won/Shopping_Mall/assets/58906858/e9c6008c-b04e-402d-ba8f-a4ec4b72138b)
```
spring boot devtools 의존성을 추가합니다.
```
#### Automatic Restart
[IntelliJ 자동빌드 설정 방법](https://velog.io/@jodawooooon/IntelliJ-%EC%9E%90%EB%8F%99-%EB%B9%8C%EB%93%9C-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95-Registry%EC%97%90-compiler.automake.allow.when.app.running%EC%9D%B4-%EC%97%86%EB%8A%94-%EA%B2%BD%EC%9A%B0)
![image](https://github.com/mr-won/Shopping_Mall/assets/58906858/93c7182a-f9e2-466a-b810-2be1fe86ff9e)     
![image](https://github.com/mr-won/Shopping_Mall/assets/58906858/f22e8b30-f9a7-49a2-8363-eb76051ae12c)       
```
21.2 버전 이전에는 shift를 두 번 눌러서 나오는 registry-compiler에서 변경을 하고 이후는 setting-advanced setting-compiler
에서 allow autom-make to start even if ~를 체크해줍니다.

file-settings-build, execution, deployment - compiler 메뉴에서 build project automatically에 체크해줍니다.
```
#### Live Reload 적용하기
![image](https://github.com/mr-won/Shopping_Mall/assets/58906858/7da3e77c-b47d-4aab-ab12-947655234e54)
```
application.properties 에 Live Reload 적용 설정을 추가합니다.
```
#### 크롬 확장 프로그램 추가
![image](https://github.com/mr-won/Shopping_Mall/assets/58906858/a9348746-8b60-4bc2-9515-71e5bc1af2e2)
```
LiveReload 확장 프로그램을 설치하고 모든 사이트에서 적용이 가능하도록 설정합니다.
```
#### Property Defaults 적용하기
![image](https://github.com/mr-won/Shopping_Mall/assets/58906858/5c5009b1-e8ca-43fe-a0c2-8de846ecdaf9)
```
pom.xml에 spring.thymeleaf.cache=faslse를 추가합니다 false는 개발환경에서 캐싱 기능을 꺼두는 방법으로
true는 운영환경에서 캐싱 기능을 키는 방법으로 관리할 수 있습니다.
```
