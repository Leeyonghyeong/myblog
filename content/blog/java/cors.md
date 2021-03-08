---
title: '[JAVA] 스프링 CORS 간단하게 설정하기'
date: 2021-03-08 00:00:00
category: 'java'
draft: false
---

자바에서 api 호출을 위해 간단하게 CORS 설정을 위한 방법이다.

나의 경우는 간단하게 어노테이션으로 설정을 해주었다.

spring-framework 4.2.x 버전 이후 부터 지원 되는

@CrossOrigin 어노테이션을 달아주기만 하면 끝이다.

```java
@CrossOrigin(origins="*")
@RestController
@RequestMapping("/api/reply")
public class testController {

    public String test() {
        return "test";
    }
}
```

```java
@RestController
@RequestMapping("/api/reply")
public class testController {

    @CrossOrigin(origins="*")
    public String test() {
        return "test";
    }
}
```

클래스 전체에 허용 하려면 클래스 위에 어노테이션을 달아주면 되고

원하는 메소드에다가만 적용을 원할 경우에는 원하는 메소드에만 적용을 해주면 된다.

```
@CrossOrigin(origins="허용주소:포트")
```

이런 식으로 특정 도메인만 접속을 허용 할 수도 있다.
