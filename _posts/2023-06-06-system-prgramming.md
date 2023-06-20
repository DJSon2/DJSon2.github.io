# 시스템 프로그래밍

# 컴파일러, 링커, 인터프리터
컴파일러, 링커, 인터프리터는 모두 프로그래밍 언어를 실행 가능한 형탤로 변환하는 도구 또는 프로그램이다. 이들의 공통점은 이와 같다.
1. 프로그래밍 언어 처리 :
    - 모두 프로그래밍 언어를 처리하는 역하을 가지고 있다.
    - 소스 코드를 이해하고, 분석하며, 실행 가능한 형태로 변환한다.
2. 실행 가능한 코드 생성 :
    - 모두 소스 코드를 실행 가능한 형태로 변환하여 컴퓨터에서 실행할 수 있게 한다.
    - 컴파일러와 링커는 기계어 코드나 중간 언어를 생성하여 실행 파일을 만들고, 인터프리터는 소스 코드를 한 줄씩 해석하여 바로 실행한다.
3. 프로그램의 실행 환경 구성 :
    - 모두 프로그램의 실행을 위해 필요한 환경을 구성한다.
    - 링커는 실행 파일에 필요한 라이브러리나 외부 모듈을 연결하여 실행 가능한 형태로 만든다.
    - 인터프리터 소스 코드의 실행을 위해 필요한 런타임 환경을 구성한다.
- 또한, 이들은 모두 소스 코드의 오류를 처리하고, 실행 도중에 발생하는 오류를 보고하는 역할도 수행한다. 하지만 각각의 동작 방식과 역할에는 차이가 있다.

# 컴파일러(Compiler)
- 컴파일러는 소스 코드를 기계어나 중간 언어로 변환하는 프로그램이다.
- 역할 
    - 소스 코드를 한 번에 전체적으로 분석하여 중간 표현 형식으로 변환한 후, 해당 표현을 기계어로 변환한다. 
    이러한 변환은 컴파일 단계에서 모두 이루어진다. 컴파일러는 전체 소스 코드를 컴파일하고 나면 실행 가능한 기계어 코드로 된 프로그램을 생성한다. 
- 이러한 프로그램은 이후 여러 번의 실행을 위해 저장되어 사용될 수 있다.

# 링커(Linker)
- 링커는 여러 개의 오브젝트 파일을 하나의 실행 가능한 파일로 결합하는 프로그램이다.
- 일반적으로 컴파일러에 의해 생성된 오브젝트 파일들은 여러 모듈로 구성되어 있다.
- 링커는 이러한 모듈들을 필요한 순서에 따라 결합하여 하나의 실행 파일로 만든다.
    - 또한, 링커는 라이브러리를 참조하여 실행 파일에 필요한 외부 함수나 데이터를 연결한다.
- 링커는 실행 파일의 로드 주소를 조정하고, 심볼들의 참조 및 정의를 해결하여 최종적으로 실행 파일을 생성한다.

# 인터프리터(Interpreter)
- 인터프리터는 소스 코드를 한 줄씩 읽어들여 바로 실행하는 프로그램이다.
- 인터프리터는 소스 코드를 실행 가능한 기계어로 변환하는 컴파일 단계가 없다.
    - 대신, 소스 코드를 읽고 해석하여 해당 기능을 바로 실행한다.
- 인터프리터는 소스 코드를 한 줄씩 해석하면서 실행하기 때문에, 오류가 발견되면 해당 줄에서 실행을 멈추고 오류를 보고한다.
- 인터프리터는 소스 코드를 실행하는 동안에도 수정과 실행을 동시에 할 수 있는 장점이 있다.