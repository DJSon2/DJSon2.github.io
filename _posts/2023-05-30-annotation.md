---
layout: single
title: Annotation(어노테이션)
---


# Annotation(어노테이션)
어노테이션은 자바 프로그래밍 언어에서 소스 코드에 메타데이터(metadata)를 추가하는 방법이다.
         
메타데이터는 데이터에 대한 설명이나 추가 정보를 제공하며, 어노테이션을 사용하여 소스 코드에 주석을 달거나 특정한 설정을 나타낼 수 있다.

# 어노테이션 목적
어노테이션은 '@'기호를 사용하여 특정 요소에 적용되며, 컴파일러, 개발 도구, 프레임워크 등에서 정보를 활용할 수 있다.
- 어노테이션은 주로 세 가지 목적으로 사용된다 :
    1. 정보 제공 :
        - 어노테이션을 사용하여 코드에 추가 정보를 제공할 수 있다.
        - 예를 들어, '@Deprecated'어노테이션은 해당 요소가 더 이상 권장되지 않음을 나타내는데 사용될 수 있다.
    2. 컴파일러 지시 :
        - 어노테이션을 사용하여 컴파일러에게 특정한 작업을 수행하도록 지시할 수 있다.
        - 예를 들어, '@Override' 어노테이션은 해당 메서드가 상위 클래스나 인터페이스의 메서드를 재정의하고 있음을 나타내며, 컴파일러는 이를 확인하여 오버라이딩의 정확성을 검사할 수 있다.
    3. 런타임 처리 : 
        - 어노테이션을 사용하여 런타임에 코드를 처리하거나 특정한 동작을 수행할 수 있다.
        - 예를 들어, 프레임워크에서 '@RequestMapping' 어노테이션을 사용하여 HTTP 요청과 해당하는 메서드를 매핑하고 처리할 수 있다.]
         
- 어노테이션은 사용자 정의할 수도 있으며, '@interface'키워드를 사용하여 어노테이션 타입을 정의할 수 있다. 어노테이션 리플렉션(reflection)을 통해 런타임에도 접근할 수 있으며, 이를 활용하여 프로그램 동작을 동적으로 변경하거나 분석하는 등 다양한 작업에 활용될 수 있다.

# 사용 예시
- @Override
    - 메소드를 오버라이드한다는 의미
```
@Override
public void getInfo() {
  System.out.println("test");
}
```

- @Deprecated
    - 메소드를 Deprecated시키는 것
```
@Deprecated
public void deprecatedMethod() {
  System.out.println("test");
}
```
- @SuppressWarnings
    - 컴파일러 경고를 출력하지 않도록 설정한다. SuppressWarnings 어노테이션은 인자를 받는데 인자에 따른 의미는 아래와 같다.
        - @SuppressWarnings("all") : 모든 경고를 억제
        - @SuppressWarnings("cast") : 타입 캐스트관련 경고 억제
        - @SuppressWarnings("dep-ann") : 사용하지 말아야할 주석 관련 경고 억제
        - @SuppressWarnings("deprecation") : Deprecated 메소드를 사용한 경우 발생하는 경고 억제
        - @SuppressWarnings("fallthrough") : switch문에서 break 구문 누락 관련 경고 억제
        - @SuppressWarnings("finally") : finally블럭 관련 경고 억제 
        - @SuppressWarnings("null") : null 관련 경고 억제
        - @SuppressWarnings("rawtypes") : 제너릭을 사용하는 클래스 매개변수가 특정되지 않았을 때의 경고 억제
        - @SuppressWarnings("unchecked") : 검증되지 않은 연산자 관련 경고 억제
        - @SuppressWarnings("unnused") : 사용하지 않는 코드 관련 경고 억제
    - 해당 어노테이션 사용 이유는 경고는 경고일 뿐, 경고 상황을 알고있는 개발자인 경우 쓸데없이 컴파일 로그가 지저분해져서 필요한 경고들이 잘 보이지 않을 수 있기 때문에 사용하게 된다.