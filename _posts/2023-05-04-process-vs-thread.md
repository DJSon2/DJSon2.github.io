---
layout: single
title: "Process vs Thread"
---


# Process and Thread
프로세스(Process)와 스레드(Tread)는 운영체제에서 프로그램을 실행하기 위해 사용되는 개념으로, 둘 다 실행 중인 코드의 실행 흐름을 나타낸다는 공통점이 있다. 하지만 다음과 같은 차이점이 존재한다.

# 프로세스(Process)
* 프로세스는 운영체제로부터 자원(I/O, 파일, 주소 공간 등)을 할당받은 실행 중인 프로그램이다.
* 각각의 프로세스는 독립된 메모리 영역을 가지고 있고, 그 각각의 프로세스는 서로 완전히 분리가 되어 있어 다른 프로세스의 자원에 직접 접근할 수 없다.
* 프로세스는 운영체제로부터 할당받은 자원을 이용하여 동작하고, 이러한 자원은 각 프로세스마다 독립적으로 할당되기 때문에 한 프로세스에서 다른 프로세스의 자원을 직접적으로 접근할 수 없다. 
* 프로세스 간 통신(Inter Process Communication, IPC)을 통해 서로 데이터를 주고 받을 수 있다.

# 스레드(Thread)
* 스레드는 프로세스 안에서 실행되는 여러 흐름의 단위이다.
* 프로세스의 자원(I/O, 파일, 주소 공간 등)을 공유하여 사용할 수 있으며, 스레드 간의 통신은 프로세스의 자원을 이용하여 이루어진다.
* 각각의 스레드는 스택을 비롯해 독립적인 실행 환경을 갖고 있지만, 프로세스 내의 메모리 공간은 서로 공유한다.
* 스레드는 프로세스 내에서 서로 다른 실행 흐름을 가질 수 있으므로, 다수의 작업을 동시에 처리할 수 있다.
* 하나의 프로세스 내에서 실행되는 스레드들은 해당 프로세스의 자원을 공유하므로, 자원 공유와 스레드 간의 동기화 문제 등 다양하고 복잡한 문제가 발생할 수 있다.

# 차이점
요약하자면, 아래와 같이 정리 할 수 있다.
* 프로세스
    * 독립적인 실행 단위
    * 각각의 프로세스는 서로 완전히 분리되어 서로의 자원에 직접 접근 불가
* 스레드
    * 하나의 프로세스 내에서 서로 다른 실행 흐름을 가질 수 있는 실행 단위
    * 프로세스의 자원을 공유하여 사용


참고 사이트
* https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/lang/Thread.html

* https://mangkyu.tistory.com/92


