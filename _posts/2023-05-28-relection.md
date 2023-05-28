---
layout: single
title: 리플렉션(Reflection)
---

# 리플렉션(Reflection)이란?
리플렉션은 구체적인 클래스 타입을 알지 못하더라도 그 클래스의 메서드, 타입, 변수들에 접근할 수 있도록 해주는 자바 API를 뜻하며,        

컴파일 시간이 아닌 실행 시간에 동적으로 특정 클래스의 정보를 추출할 수 있는 프로그래밍 기법이라 할 수 있다.

## 리플렉션 원리
자바의 리플렉션은 런타임시에 클래스의 구조와 멤버들을 동적으로 조사하고 조작할 수 있는 기능이다. 
      
- 이 원리를 이용해 클래스의 메소드, 필드, 생성자 등에 접근하고 실행할 수 있다.
- 이를 통해 프로그램 실행 중에 동적으로 클래스를 분석하고 조작하는 것이다.

# 리플렉션에 포함된 주요 기능
리플렉션을 사용하는 주요한 클래스는 'java.lang.reflect' 패키지에 포함되어 있다.        
- 리플렉션을 사용할 수 있는 몇 가지 주요한 기능과 메소드
    1. 클래스 정보 가져오기 :
        - 'Class' 클래스를 사용하여 클래스의 정보를 가져올 수 있다.
            - 예를 들어,'Class.forName()'메소드를 사용하여 동적으로 클래스를 로드하고 'Class'객체를 얻을 수 있다.
    2. 멤버 접근 :
        - 'Class'객체를 통해 클래스의 메소드, 필드, 생성자 등에 접근할 수 있다.
        - 'getMethod()', 'getField()', 'getConstructor()' 등의 메소드를 사용하여 해당 멤버들의 정보를 가져올 수 있다.
    3. 멤버 실행 :
        - 'Method' 객체를 사용하여 메소드를 실행 할 수 있다.
        - 'invoke()' 메소드를 사용하여 특정 객체에 대해 메소드를 호출하고 실행할 수 있다.
    4. 필드 조작 : 
        - 'Field' 객체를 사용하여 필드 값을 가져오거나 설정할 수 있다.
        - 'get()' 및 'set()'메소드를 사용하여 해당 필드의 값을 읽거나 변경할 수 있다.
    5. 생성자 활용 :
        - 'Constructor' 객체를 사용하여 객체의 인스턴스를 생성할 수 있다.
        - 'newInstance()' 메소드를 사용하여 생성자를 호출하여 새로운 객체를 동적으로 생성할 수 있다.

# 리플렉션을 유용하게 사용할 수 있는 상황
- 런타임에 클래스 정보를 동적으로 조사하고 조작해야 할 때
- 외부 라이브러리의 클래스를 사용해야 할 때
- 자동화된 코드 검사 도구나 프레임워크를 개발할 때
- 개발 도구나 개발 환경을 구축할 때
       
# 리플렉션을 사용할 때
- 리플렉션은 유연성과 동적인 기능을 제공하지만,
    사용하기 전에 성능상의 오버헤드가 있다는 점과 캡슐화를 위반할 수 있는 가능성을 고려해야한다. 
- 리플렉션은 필요한 경우에 한정적으로 사용하는 것이 좋다.
- 결론적으로, 리플렉션은 자바에서 강력한 동적 기능을 제공하지만, 사용할 때 주의해야 할 점도 있다.
- 성능 상의 오버헤드와 캡슐화 위반 등을 고려하여 적절하게 사용해야 한다.

# 리플렉션 사용 예시
1. 클래스 정보 가져오기 :
```
// 클래스 이름으로 클래스 정보 가져오기
Class<?> clazz = Class.forName("com.example.DJClass");

// 클래스의 이름 가져오기
String className = clazz.getName();

// 클래스의 메소드 정보 가져오기
Method[] methods = clazz.getMethods();

// 클래스의 필드 정보 가져오기
Field[] fields = clazz.getFields();

```

2. 메소드 실행 :
```
// 메소드 실행
Method method = clazz.getMethod("myMethod", int.class, String.class);
Object instance = clazz.newInstance();
Object result = method.invoke(instance, 10, "안녕");
```

3. 필드 조작 :
``` 
// 필드 값 가져오기
Field field = clazz.getField("myField");
Object instance = clazz.newInstance();
Object value = field.get(instance);

// 필드 값 설정하기
field.set(instance, "New Value");
```

4. 생성자 활용 :
```
// 생성자를 사용하여 인스턴스 생성
Constructor<?> constructor = clazz.getConstructor(int.class, String.class);
Object instance = constructor.newInstance(10, "안녕");
```