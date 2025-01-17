---
layout: single
title: 디자인 패턴과 안티 디자인 패턴
---

# Design Patter(디자인 패턴)
- 디자인 패턴은 소프트웨어 설계에서 자주 발생하는 문제들에 대한 해결책이나 재사용 가능한 설계 방법을 제공하는 템플릿이다.
- 디자인 패턴은 경험과 모범 사례를 바탕으로 개발자들이 개발 과정에서 마주치는 문제를 해결하기 위해 사용된다.
- 이러한 패턴들은 시스템의 유연성, 재사용성, 확장성을 향상시키고, 코드의 가독성과 유지 보수성을 개선하는데 도움을 준다.

# 디자인 패턴 종류
디자인 패턴의 종류는 크게 세 가지 범주로 나눌 수 있다.
1. 생성(Creational) 패턴 :
    - 객체의 생성과 초기화에 관련된 패턴이다.
    - 주로 객체 생성 과정의 유연성과 확장성을 제공하며, 객체 간의 결함도를 줄이고 클라이언트 코드로부터 객체 생성을 캡슐화 한다.
    - 대표적인 생성 패턴 종류
        - 싱글톤(Singleton), 팩토리 메서드(Factory Method), 추상 팩토리(Abstract Factory), 빌더(Builder), 프로토타입(Prototype) 패턴 등 
2. 구조(Structural) 패턴 :  
    - 객체들의 구성을 조합하여 더 큰 구조를 형성하는 패턴이다.
    - 클래스나 객체 간의 상호 작용을 조직화하고, 객체들 사이의 관계를 정의한다.
    - 주로 시스템의 구조를 더욱 유연하고 효율적으로 만들며, 서로 다른 인터페이스를 가진 객체들을 함께 동작시키는데 사용된다.
    - 대표적인 구조 패턴 종류
        - 어댑터(Adapter), 브리지(Bridge), 컴포지트(Composite), 데코레이터(Decorator), 퍼싸드(Facade) 프록시(Proxy) 패턴 등
3. 행위(Behavioral) 패턴 : 
    - 객체들 사이의 알고리즘, 책임, 행위를 관리하는 패턴이다.
    - 주로 객체들 간의 상호작용과 책임 분배를 조정하고, 알고리즘의 유연성과 재사용성을 촉진한다.
    - 대표적인 행위 패턴 종류
        - 옵저버(Observer), 스트래티지(Strategy), 템플릿 메서드(Template Method), 인터프리저(Interpreter), 커맨드(Command), 상태(State), 이터레이터(Interator) 패턴 등

# Anti Pattern(안티 디자인 패턴)
- 안티 디자인 패턴은 반대로 잘못된 설계나 구현으로 인해 발생하는 문제들을 설명하는 패턴이다. 
- 이러한 패턴들은 비효율적인 코드, 유지보수 어려움, 성능 저하 등을 야기할 수 있다.
- 안티 디자인 패턴의 목적은 이러한 문제들을 식별하고 해결책을 제시하여 개발자들이 반복적인 실수를 피하고 품질이 높은 소프트웨어를 개발하는데 도움을 주는 것이다.

# 안티 디자인 패턴 종류
일부 유명한 안티 디자인 패턴은 다음과 같다.
1. 싱글톤(Singleton) 남용 : 
    - 너무 많은 객체를 싱글톤으로 구현하여 유연성과 테스트 가능성을 감소시키는 패턴
2. 거대한 클래스(Monolithic Class) :
    - 한 가지 기능을 수행하기 위해 너무 많은 역할과 책임을 갖는 클래스를 만드는 패턴
3. 긴 메서든(Long Method) :
    - 너무 많은 코드를 한 메서드에 모으는 패턴으로, 가독성과 유지 보수성을 감소 시킴
       
- 안티 디자인 패턴은 잘못된 설계의 예를 보여주기 때문에 이러한 상황을 피하고 좋은 소프트웨어 설계를 위해 경계를 설정하는데 도움을 준다.