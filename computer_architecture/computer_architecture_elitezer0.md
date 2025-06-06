# 컴퓨터 구조 정리

![[Pasted image 20250420205800.png]]
## 1. 컴퓨터가 이해하는 정보

### 데이터

- 정적인 정보
- 명령어에 종속된 정보: 명령의 대상 또는 명령어의 재료

### 명령어

- 수행할 동작과 대상에 대한 정보
- 명령어를 이해하고 실행하는 주체: **CPU**
- CPU 종류에 따라 실행 가능한 명령어 및 처리 방식이 달라짐

## 2. 컴퓨터의 핵심 부품

![[Pasted image 20250420205923.png]]

### CPU (중앙처리장치)

![[Pasted image 20250420210035.png]]

- 정보를 읽고 해석하고 실행하는 부품
- 구성 요소:
    - **ALU(산술논리연산장치)**: 연산 수행 회로
    - **CU(제어장치)**: 제어 신호를 통해 부품 작동
    - **레지스터**: 임시 저장장치 (명령어, 데이터 저장)

### 메모리 (주기억장치)

![[Pasted image 20250420210259.png]]

- **RAM**: 실행 중인 프로그램의 데이터와 명령어 저장
- 주소를 통해 접근
- **휘발성**: 전원이 꺼지면 정보가 사라짐

### 캐시 메모리

- CPU와 메모리 간 속도 차이를 줄이기 위한 저장장치 (SRAM 기반)
- **L1, L2, L3 캐시**
    - L1: 코어 내부 (명령어/데이터 분리형)
    - L2: 코어 내부
    - L3: 코어 외부

### 보조기억장치

- 비휘발성 저장장치
- 프로그램 보관 용도
- **RAID** 기술 활용 가능 (성능/안정성 강화)

### 입출력장치

- 컴퓨터 외부와의 정보 교환 담당
- 보조기억장치와 함께 **주변장치**라고 통칭

### 메인보드와 버스

![[Pasted image 20250420212646.png]]

- **메인보드**: 부품 연결을 위한 슬롯 및 단자 제공
- **버스**: 부품 간 정보 통로
    - **시스템 버스**: CPU, 메모리 등 핵심 부품 연결

![[Pasted image 20250420212737.png]]


## 3. 컴퓨터의 정보 표현 방식

### 비트 (bit)

- 0과 1을 표현하는 최소 단위
- N비트: 2^N 개의 정보 표현 가능

![[Pasted image 20250420212856.png]]

### 16진수

|십진수|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|16진수|0|1|2|3|4|5|6|7|8|9|A|B|C|D|E|F|

- 2진수로의 변환이 편리
- `16진수` : 0xAD = 0b10101101 `2진수` : 0xA = 0b1010 `2진수`: 0xD = 0b1101 이 둘을 이어 붙이면 됨.
### 실수 표현

- 부동 소수점 방식 사용
- 10진수와 2진수 소수의 표현 차이로 오차 발생 가능

### 문자 집합과 인코딩

- **문자 인코딩**: 문자를 0과 1로 변환
- **문자 디코딩**: 코드 → 사람이 이해할 수 있는 문자
- **ASCII**: 7비트로 128개 문자 표현
    - 주요 코드: 0(NULL), 32(공백), 48('0'), 65('A'), 97('a')
- **EUC-KR**: 한글 2바이트 표현, 약 2,350자 표현 가능
- **유니코드**: 전 세계 문자 통합 표현
    - **UTF-8, UTF-16, UTF-32** 등의 가변 길이 인코딩 사용


## 4. 명령어 구조와 실행

![[Pasted image 20250420220836.png]]

### 명령어 구성

- **연산코드**: 수행할 동작 (데이터 전송, 연산, 제어, 입출력 등)
	
	![[Pasted image 20250420221328.png]]![[Pasted image 20250420221347.png]]

- **오퍼랜드**: 동작 대상 또는 주소

### 기계어와 어셈블리어

- **기계어**: 0과 1로 구성된 명령어
- **어셈블리어**: 기계어를 사람이 이해하기 쉬운 형식으로 표현
- 플랫폼 의존적 → 특정 CPU에서만 실행 가능

### 명령어 사이클

![[Pasted image 20250420221932.png]]

1. **인출 사이클**: 메모리에서 명령어 읽기
2. **간접 사이클**: 필요한 데이터 주소 접근
3. **실행 사이클**: 명령어 실행
4. **인터럽트 사이클**: 인터럽트 발생 시 처리

# CPU

## 레지스터

레지스터는 CPU 안에 있는 작은 임시 저장장치
각기 다른 이름과 역할이 있음
1. 프로그램 카운터
	- 메모리에서 다음으로 읽어 들일 명령어의 주소를 저장
	- 명령어 포인터라고 부르는 CPU도 존재
	- 일반적으로 프로그램 카운터는 1씩 증가
	- 다만 프로그램의 실행 흐름이 순차적이지 않을 때는 프로그램 카운터 값이 임의의 위치로 변경  
2. 명령어 레지스터
	- 해석할 명령어를 저장하는 레지스터
3. 범용 레지스터
	- 데이터와 명령어 주소 모두 저장. 일반적인 상황에서 자유롭게 사용
4. 플래그 레지스터
	- 연산의 결과 혹은 CPU 상태에 대한 부가 정보인 플래그 값을 저장
	![[Pasted image 20250420222505.png]]
5. 스택 포인터
	- 메모리 내 스택 영역의 최상단 스택 데이터 위치를 가리키는 레지스터
	- 마지막으로 스택에 저장된 데이터의 위치를 가리키는 레지스터이자, 스택이 채워진 정도를 나타내는 레지스터 

## 인터럽트

CPU 작업을 방해하는 신호

동기 인터럽트
- CPU에 의해 발생하는 인터럽트
- 프로그래밍 오류와 같은 예외적인 상황을 마주쳤을 때 발생
- 동기 인터럽트는 예외(exception)라고도 부름

비동기 인터럽트
- 입출력장치에 의해 발생
- 일반적으로 비동기 인터럽트를 인터럽트라고 지칭함
- 다만 책에서는 용어 혼동을 방지하기 위해 하드웨어 인터럽트라는 용어 사용

### 하드웨어 인터럽트

효율적으로 명령어를 처리하기 위해 사용

CPU가 하드웨어 인터럽트를 처리하는 순서
1. 입출력 장치는 CPU에 인터럽트 요청 신호를 보냄
2. CPU는 실행 사이클이 끝나고 명령어를 인출하기 전 인터럽트 여부 확인
3. CPU는 인터럽트 요청을 확인하고, 인터럽트 플래그를 통해 현재 인터럽트를 받아들일 수 있는지 여부 확인
4. 인터럽트를 받아들일 수 있다면 CPU가 지금까지의 작업을 백업
5. CPU는 인터럽트 벡터를 참조하여 인터럽트 서비스 루틴 실행
6. 인터럽트 서비스 루틴 실행이 끝나면 4에서 백업한 작업을 복구하여 실행을 재개

인터럽트는 CPU의 정상적인 실행 흐름을 끊는 것. 인터럽트 전에 CPU에 가능 여부를 확인해야 함(= 인터럽트 요청 신호)
인터럽트 요청을 수용하기 위해 플래그 레지스터의 인터럽트 플래그 활성화되어 있어야 함
하지만 모든 하드웨어 인터럽트를 인터럽트 플래그로 막을 수 있는 것은 아님
정전이나 하드웨어 고장으로 인한 인터럽트가 이에 해당.
하드웨어 인터럽트에는 인터럽트 플래그로 막을 수 있는 인터럽트와 막을 수 없는 인터럽트(NMI라고 부름)가 있음. 
인터럽트 서비스 루틴은 인터럽트를 처리하기 위한 프로그램(인터럽트 핸들러 라고도 부름)
어떤 인터럽트가 발생했을 때 해당 인터럽트를 어떻게 처리하고 작동해야할지에 대한 정보로 이루어진 프로그램
CPU의 인터럽트 처리는 인터럽트 서비스 루틴을 실행하고 본래 수행하던 작업으로 다시 되돌아온다는 뜻

![[Pasted image 20250420223456.png]]
인터럽트 벡터는 인터럽트 서비스 루틴을 식별하기 위한 정보
인터럽트  처리 시 요청 직전까지 수행하던 작업 내용을 다시 재개하기 위해 필요한 모든 내용은 스택에 백업

![[Pasted image 20250420223953.png]]
## 예외

![[Pasted image 20250420225220.png]]

- **폴트**: 예외 발생 명령어부터 재실행
- **트랩**: 다음 명령어부터 실행
- **중단**: 프로그램 강제 종료
- **소프트웨어 인터럽트**: 시스템 콜 등(3장에서 더 깊이 학습)

## CPU 성능 향상

### CPU 클럭 속도

클럭 : 컴퓨터 부품을 일사불란하게 움직일 수 있게 하는 시간의 단위
클럭속도 : 헤르츠 단위로 측정 클럭이 1초에 몇 번 반복되는지 CPU의 속도 단위로 간주되기도 함

### 멀티코어와 멀티스레드

코어 : CPU 내에서 명령어를 읽어들이고, 해석하고 실행하는 부품 의미
여러개의 코어를 포함하고 있는 CPU는 멀티코어 CPU 멀티코어 프로세서라고 부름
하드웨어 스레드란 하나의 코어가 동시에 처리하는 명령어의 단위 ->논리 프로세서라고 부르기도 함
소프트웨어 스레드란 하나의 프로그램에서 독립적으로 실행되는 단위
병렬성 : 작업을 물리적으로 동시에 처리하는 성질
동시성 : 동시에 작업을 처리하는 것처럼 보이는 성질

### 파이프라이닝을 통한 명령어 병렬 처리

명령어 병럴처리 기법 : 여러 명령어를 통시에 처리하여 CPU를 한시도 쉬지 않고 작동시킴으로써 CPU 성능을 높이는 기법
단계가 겹치지 않는다면 CPU는 각각의 단계를 동시에 실행 가능
명령어들을 명령어 파이프라인에 넣고 동시에 처리하는 기법을 명령어 파이프라이닝이라고 한다.

#### CISC (Complex Instruction Set Computer)
- 복잡한 명령어를 한 개의 명령어로 처리할 수 있도록 설계된 구조임  
- 하나의 명령어로 여러 작업을 처리할 수 있으므로 명령어 수가 적고 코드 밀도가 높음  
- 메모리 접근이 자유롭고 다양한 주소지정방식을 지원함  
- 하드웨어가 복잡하며 명령어 디코딩 시간이 길어질 수 있음  
- 마이크로코드 방식으로 명령어를 구현하므로 제어장치 설계가 복잡함  
- 대표적인 예로는 인텔 x86 계열이 있음  

#### RISC (Reduced Instruction Set Computer)

- 단순하고 적은 수의 명령어로 구성된 구조임  
- 명령어 실행 시간이 일정하고 빠르며 파이프라이닝에 유리함  
- 대부분의 명령어가 한 사이클 내에 실행되도록 설계되어 있음  
- 메모리 접근은 로드/스토어 명령어를 통해서만 가능함  
- 하드웨어는 비교적 단순하며 컴파일러의 역할이 중요함  
- 대표적인 예로는 ARM, MIPS, SPARC 등이 있음  

#### CISC vs RISC 비교

| 항목              | CISC                                | RISC                              |
|------------------|-------------------------------------|-----------------------------------|
| 명령어 수        | 많음                                | 적음                              |
| 명령어 복잡도    | 복잡함                              | 단순함                            |
| 실행 속도        | 느릴 수 있음                        | 빠름                              |
| 파이프라이닝     | 구현이 어려움                        | 구현이 쉬움                        |
| 메모리 접근      | 다양한 방식 지원                    | 제한적 (Load/Store 방식)          |
| 하드웨어 복잡도  | 높음                                | 낮음                              |
| 대표 아키텍처    | x86                                 | ARM, MIPS                         |

# 메모리
## RAM
휘발성 저장장치
임의 접근 메모리
임의 접근이란 저장된 요소에 순차적으로 접근할 필요 없이 임의의 위치에 곧장 접근 가능한 방식을 의미
직접 접근이라고도 부름
순차접근은 이름 그대로 위치에 저장된 요소에 접근하기 위해 처음부터 순차적으로 접근하는 방식
- DRAM
	시간이 지나면 저장된 데이터가 정참 사라지는 RAM
- SRAM
	시간이 지나도 저장된 데이터가 사라지지 않는 RAM
- SDRAM
	클럭신호와 동기화된 발전된 형태의 DRAM
- DDR SDRAM
	대역폭을 넓혀 속도를 빠르게 만든 SDRAM
## 빅 엔디안과 리틀 엔디안
메모리는 대부분 데이터를 바이트 단위로 저장하고 관리
빅 엔디안은 낮은 번지의 주소에 상위 바이트부터 저장하는 방식
리틀 엔디안은 낮은 번지의 주소에 하위 바이트부터 저장하는 방식

## 캐시 메모리

CPU의 연산 속도와 메모리 접근 속도의 차이를 줄이기 위해 탄생한 저장장치
SRAM 기반의 저장장치
코어와 가장 가까운 캐시 메모리를 L1 캐시 그다음으로 가까운 캐시 L2 캐시 그 다음 L3캐시
L1 L2는 코어 내부 L3는 코어 외부
L1 캐시의 경우 명령어만을 저장하는 L1I 캐시 데이터만을 저장하는  L1D 캐시 이러한 유형을 분리형 캐시

### 캐시 히트와 캐시 미스
캐시 메모리가 예측하여 저장한 데이터가 CPU에 의해 실제로 사용되는 경우를 캐시히트
자주 사용될것으로 예측하여 저장했지만 틀린 예측으로 필요한 데이터를 직접 가져와야하는 경우 캐시 미스
캐시가 히트되는 비율을 캐시 적중률이라고 하며,
캐시 히트 회수/ (캐시히트 + 캐시미스) 로 계산
일반적인 컴퓨터의 캐시 적중률은 85~95%

### 참조 지역성의 원리
참조 지역성의 원리 : cpu가 메모리에 접근할 떄 보이는 주된 경향
시간 지역성 : cpu는 최근에 접근했던 메모리 공간에 다시 접근하려는 경햐잉 있음
	- 변수
공간 지역성: cpu는 접근한 메모리 공간의 근처에 접근하려는 경향이 있다.
	 - 배열

### 캐시 메모리의 쓰기 정책과 일관성

즉시 쓰기 : 메모리를 항상 최신 상태로 유지
버스의 사용시간과 쓰기 시간이 늘어남

지연쓰기 : 캐시 메모리에만 값을 써두었다가 추후 수정된 데이터를 한 번에 메모리에 반영
메모리 접근 횟수를 줄여 속도는 빠르지만 메모리와 캐시 메모리 간의 일관성이 깨질 수 있음

# 보조기억장치와 입출력장치

## RAID
하드디스크드라이브
플래시 메모리 기반 저장장치
플래시 메모리는 전기적인 방식5으로 데이터를 읽고쓰는 반도체 기반의 저장장치 대표적으로 SSD
RAID는 데이터의 안정성 혹은 성능을 확보하기 위해 여러개의 독립적인 보조기억장치를 하나의 보조기억장치처럼 사용하는 기술
RAID0은 단순하게 나누어 저장하는 구성방식
RAID1은 완전한 복사본을 만들어 저장하는 구성방식 미러링이라고도 함
RAID4는 패리티 정보를 저장하는 디스크를 따로 두는 구성 방식 패리티란 오류를 검출할 수 있는 정보
RAID5는 패리티를 분산하여 저장하는 구성방식
RAID6는 서로 다른 2개의 패리티를 두는 구성방식. 오류를 검출하고 복구할 수 있는 수단이 2개가 되는 것

## 입출력 기법

### 장치 컨트롤러와 장치 드라이버
장치 컨트롤러는 CPU와 입출력장치 사이의 통신을 중갯하는 중개자 역할의 하드웨어
장치 드라이버는 장치 컨트롤러의 동작을 알고, 장치 컨트롤러가 컴퓨터 내부와 정보를 받을 수 있도록 하는 프로그램

### 프로그램 입출력
프로그램 입출력은 프로그램 속 명령어로 입출력 작업을 수행하는 방법
입출력 명령어를 실행함으로써 장치 컨트롤러와 상호작용할 수 있고, 이를 통해 입출력 작업을 수행

### 인터럽트 기반 입출력: 다중 인터럽트
흔히 다중 인터럽트를 처리하기 위해서는 프로그래머블 인터럽트 컨트롤러(PIC)라는 하드웨어가 사용된다.

### DMA 입출력
직접 메모리에 접근할 수 있는 입출력 기능

# 추가 정리

파이프라이닝이 병렬성을 보장하고, 동시성을 보장한다고는 말하지 않는 이유는 `작업을 동시에 수행`하는 게 아니라 `여러 작업의 서로 다른 단계를 동시에 수행`하기 때문

1. **동시성(Concurrency)**
    
    - 여러 작업을 `논리적`으로 동시에 처리
        
    - 실제로 한 번에 한 작업만 수행하더라도, 빠르게 전환하면서 동시에 처리하는 것처럼 보이게 할 수있다.
        
    - 동시성은 진짜 동시에 하지 않아도 되고, 문맥 전환(context switch)을 잘 하면 되는 것
        
2. **병렬성(Parallelism)**
    
    - 여러 작업을 `물리적으로` 동시에 수행
        
    - 여러 개의 코어에서 여러 작업이 실제로 동시에 실행되는 것과 같다.
        

---

### 파이프라이닝

- 작업을 여러 단계로 쪼갠 다음 각 단계를 `물리적`으로 `동시`에 처리하는 구조
	(ex. 1단계: 명령어 가져오기, 2단계: 디코딩, 3단계: 실행, ...)
        
    즉, **서로 다른 작업의 서로 다른 단계를 동시에** 수행
    
    - `동시`에 `여러 작업`이 실행 중(병렬성 O)
        
    - 단, 하나의 작업은 순서대로 단계(stage)를 거쳐야 하므로 한 작업을 동시에 여러 단계에서 처리하는 것은 아님(동시성 X)

# 추가정리

### 1. **스래싱이 일어나면 다른 또 중요한 작업(네트워크 작업)도 더뎌질 수 있는가?**

그럴 수 있다.

- **스래싱(Thrashing)**이란, 프로세스가 메모리보다 더 많은 페이지를 요구해 페이지 폴트가 자주 발생하면서 **계속해서 디스크와 메모리 간의 페이지 교체 작업만 반복**하는 상태    
- 이 경우 **CPU가 실제 작업보다는 페이지 교체(디스크 입출력)에만 집중하게 되어** CPU 사용률이 오히려 낮아지고 전체 시스템 응답 속도도 저하    
- **네트워크 작업**도 커널 공간의 **버퍼**, **드라이버**, **인터럽트 핸들러** 등 다양한 메모리 리소스를 필요로 하기 때문에, 스래싱으로 인해 **메모리 압박이 가해지면 네트워크 처리가 지연**될 수 있다.
- 또한 디스크 입출력 장치가 페이지 교체로 바쁘면, 네트워크 관련 데이터를 쓰거나 읽는 I/O 작업도 영향을 받을 수 있다.

### 2. **연속 메모리 할당이 참조 지역성(Locality of Reference)의 원리와 관련이 있는가?**

있다.

- **참조 지역성**이란, 프로그램이 일정한 시점에 특정 메모리 주소 근처의 데이터를 반복해서 참조하는 성질
    - **시간 지역성**: 최근 접근한 메모리에 곧 다시 접근할 확률이 높음
    - **공간 지역성**: 최근 접근한 주소와 가까운 주소에 곧 접근할 확률이 높음
        
- **연속 메모리 할당**은 물리적으로 연속된 주소 공간을 할당함으로써, **공간 지역성**을 더 잘 활용할 수 있다. 예:
    - 배열을 순차적으로 접근할 때, CPU는 캐시나 프리페치(pre-fetch) 등을 활용해 다음 데이터를 미리 가져와 성능을 향상시킴
    - 연속된 할당이면 메모리 접근 패턴이 예측 가능하므로 하드웨어가 최적화를 하기 쉬워짐짐
 
### 3. **페이지 테이블을 조회하는 부분은 정확히 어느 시점에 일어나는가?**

가상 주소 → 물리 주소 변환 시점

- 프로세스가 명령어를 실행할 때마다 참조하는 주소는 가상 주소(Virtual Address)
- MMU(Memory Management Unit)는 이 가상 주소를 **페이지 번호 + 페이지 오프셋**으로 나누고, 페이지 번호에 해당하는 페이지 테이블 항목을 찾아 물리 주소로 변환
- 이 과정은 매 주소 참조 시마다 일어남

> 단, 이 변환 작업을 빠르게 하기 위해 TLB(Translation Lookaside Buffer)를 사용해 캐싱

### 4. **TLB는 어디에 위치하고 있길래 더 빠른가?**

TLB는 CPU 안의 MMU 내부 혹은 매우 가까운 캐시에 존재

- TLB는 CPU의 캐시 수준(L1이나 MMU 내부)에 존재하며, 페이지 테이블보다 훨씬 빠르게 접근 가능    
- 페이지 테이블은 메인 메모리에 있으며, 접근 시 **DRAM latency(수십~수백 ns)**가 필요하지만, TLB는 **몇 ns 이하로 매우 빠른 응답 시간**을 가지므로 주소 변환이 빨라짐

### 5. **TLB는 정확히 어느 시점에 작동하는가?**

가상 주소 접근 직전에 작동

- 주소 참조 시, MMU가 먼저 **TLB에서 해당 가상 주소에 대한 물리 주소 매핑이 존재하는지 확인**  
- **TLB 히트**: 바로 물리 주소를 가져와 접근    
- **TLB 미스**: 페이지 테이블을 조회하여 매핑하고, 그 결과를 TLB에 저장(캐시)

### 6. **페이지 폴트는 느린데 그럼 언제 쓰는 게 좋은가?**

**페이지 폴트는 '예외 상황'으로 느리지만, 전체 메모리를 효율적으로 사용할 수 있게 한다.**

- **언제 발생하나?**
    - 프로세스가 접근하려는 **페이지가 메모리에 없을 때** (예: 디스크에 있음)
        
- 이때 OS는:
    1. 디스크에서 해당 페이지를 로드
    2. 물리 메모리에 올림
    3. 페이지 테이블을 갱신
    4. 프로세스를 재개

**하지만 쓰는 이유는:**

- 전체 프로그램을 **한 번에 다 메모리에 올릴 필요 없이**, 필요한 부분만 로드하여 **메모리 사용량 절감**
- 여러 프로그램이 동시에 실행될 수 있는 **멀티태스킹 환경** 제공
- **지연 로딩(lazy loading)**이나 **데이터 기반 프로그램(대형 DB, 이미지, 영상 등)**에서 유용
