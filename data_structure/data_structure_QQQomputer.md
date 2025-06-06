# 📊 자료구조 개념 정리

## 1. 자료구조의 큰 그림

자료구조(data structure)는 이름 그대로 어떠한 구조로 데이터를 다룰지에 대해 학습하는 과목입니다. 자료구조와 연관된 과목인 알고리즘에 대해서도 함께 알아보겠습니다.

### 자료구조와 알고리즘

- **자료구조**: 데이터를 효율적으로 저장하고 관리하는 방법
- **알고리즘**: 어떤 목적을 이루기 위해 필요한 일련의 연산 절차

자료구조와 알고리즘은 밀접한 연관성이 있습니다. 어떤 자료구조가 사용되었느냐에 따라 사용 가능한 알고리즘이 달라질 수 있습니다.

### 시간 복잡도와 공간 복잡도

- **시간 복잡도**: 입력의 크기에 따른 프로그램 실행 시간의 관계
  - 연산 횟수에 비례하므로 입력 크기에 따른 연산 횟수로 간주됨
  
- **공간 복잡도**: 프로그램이 실행되었을 때 필요한 메모리 자원의 양
  - 입력에 따른 메모리 사용량의 척도

- **빅 오 표기법(Big O Notation)**: 함수의 점근적 상한을 표기하는 방법
  - 시간 복잡도를 표현할 때 주로 사용
  - 입력 크기가 무한대로 커질 때 실행 시간의 상한을 표현
  - 계수와 낮은 차수의 항은 무시하고 최고차항의 차수만 고려

- **대표적인 시간 복잡도 (빠른 순)**:
  - O(1): 상수 시간 복잡도
  - O(log n): 로그 시간 복잡도
  - O(n): 선형 시간 복잡도
  - O(n log n): 선형 로그 시간 복잡도
  - O(n²): 이차 시간 복잡도
  - O(2ⁿ): 지수 시간 복잡도
  - O(n!): 팩토리얼 시간 복잡도

## 2. 배열과 연결 리스트

### 배열

- **정의**: 메모리에 순차적으로 저장된 같은 타입의 변수 집합
- **특징**:
  - 인덱스를 통한 접근이 O(1)로 매우 빠름
  - 크기가 고정됨 (정적 배열의 경우)
  - 삽입/삭제가 O(n)으로 상대적으로 느림 (요소 이동 필요)
  - 메모리에 연속적으로 할당됨

- **배열 연산의 시간 복잡도**:
  - 접근(Access): O(1)
  - 검색(Search): O(n) (정렬되지 않은 경우)
  - 삽입(Insert): O(n)
  - 삭제(Delete): O(n)

- **정적 배열과 동적 배열**:
  - **정적 배열**: 프로그램 실행 전에 크기가 고정된 배열
  - **동적 배열**: 실행 과정에서 크기가 변할 수 있는 배열 (Vector라고도 함)

### 연결 리스트

- **정의**: 노드의 모음으로 구성된 자료구조, 각 노드는 데이터와 다음 노드를 가리키는 포인터로 구성
- **특징**:
  - 동적으로 크기 조절 가능
  - 삽입/삭제가 O(1)로 빠름 (위치를 알고 있을 경우)
  - 특정 위치에 접근하는 데 O(n) 시간 소요
  - 메모리에 연속적으로 할당되지 않음

- **연결 리스트 연산의 시간 복잡도**:
  - 접근(Access): O(n)
  - 검색(Search): O(n)
  - 삽입(Insert): O(1) (위치를 알고 있을 경우)
  - 삭제(Delete): O(1) (위치를 알고 있을 경우)

- **연결 리스트의 종류**:
  - **단일 연결 리스트(Singly Linked List)**: 각 노드가 다음 노드만 가리킴
  - **이중 연결 리스트(Doubly Linked List)**: 각 노드가 이전 노드와 다음 노드를 모두 가리킴
  - **환형 연결 리스트(Circular Linked List)**: 마지막 노드가 첫 번째 노드를 가리키는 형태

## 3. 스택과 큐

### 스택

- **정의**: 한 쪽 끝에서만 데이터를 삽입하고 삭제할 수 있는 LIFO(Last In First Out) 자료구조
- **주요 연산**:
  - Push: 스택의 맨 위에 요소 추가
  - Pop: 스택의 맨 위 요소 제거 및 반환
  - Peek/Top: 스택의 맨 위 요소 확인 (제거하지 않음)
  - isEmpty: 스택이 비어있는지 확인

- **활용 사례**:
  - 함수 호출(Call Stack)
  - 괄호 검사
  - 웹 브라우저의 뒤로가기 기능
  - 실행 취소(Undo) 기능

### 큐

- **정의**: 한 쪽에서는 삽입, 다른 쪽에서는 삭제가 이루어지는 FIFO(First In First Out) 자료구조
- **주요 연산**:
  - Enqueue: 큐의 뒤에 요소 추가
  - Dequeue: 큐의 앞에서 요소 제거 및 반환
  - Front: 큐의 맨 앞 요소 확인 (제거하지 않음)
  - isEmpty: 큐가 비어있는지 확인

- **큐의 종류**:
  - **선형 큐(Linear Queue)**: 기본적인 큐의 형태
  - **원형 큐(Circular Queue)**: 배열의 처음과 끝이 연결된 형태
  - **덱(Deque, Double-Ended Queue)**: 양쪽 끝에서 삽입과 삭제가 모두 가능한 큐
  - **우선순위 큐(Priority Queue)**: 우선순위가 높은 데이터가 먼저 나오는 큐

## 4. 해시 테이블

- **정의**: 키-값 쌍을 저장하는 자료구조, 해시 함수를 사용하여 키를 배열의 인덱스로 변환
- **구성 요소**:
  - 해시 함수: 키를 인덱스로 변환
  - 버킷: 데이터가 저장되는 배열의 각 요소

- **해시 함수**: 임의의 길이를 가진 데이터를 고정된 길이의 데이터로 변환하는 단방향 함수
  - 대표적인 해시 알고리즘: MD5, SHA-1, SHA-256, SHA-512, SHA3, HMAC

- **해시 테이블 연산의 시간 복잡도**:
  - 접근(Access): O(1) (평균 경우)
  - 검색(Search): O(1) (평균 경우)
  - 삽입(Insert): O(1) (평균 경우)
  - 삭제(Delete): O(1) (평균 경우)
  - 최악의 경우(해시 충돌이 많을 때): O(n)

- **해시 충돌 해결 방법**:
  - **체이닝(Chaining)**: 충돌이 발생한 데이터를 연결 리스트로 추가
  - **개방 주소법(Open Addressing)**: 충돌이 발생했을 때 다른 버킷을 찾아 저장
    - 선형 조사법(Linear Probing): 충돌 발생 시 순차적으로 다음 버킷 확인
    - 이차 조사법(Quadratic Probing): 충돌 발생 시 제곱수만큼 떨어진 버킷 확인
    - 이중 해싱(Double Hashing): 두 번째 해시 함수를 사용하여 다음 위치 결정

## 5. 트리

- **정의**: 계층적 구조를 표현하는 비선형 자료구조, 노드와 간선으로 구성

- **용어**:
  - 노드(Node): 데이터를 저장하는 기본 요소
  - 간선(Edge): 노드를 연결하는 선
  - 루트 노드(Root Node): 트리의 최상위 노드
  - 부모 노드(Parent Node): 특정 노드의 상위 노드
  - 자식 노드(Child Node): 특정 노드의 하위 노드
  - 형제 노드(Sibling Node): 같은 부모를 가진 노드
  - 리프 노드(Leaf Node): 자식이 없는 노드
  - 레벨(Level): 루트에서 특정 노드까지의 경로 길이
  - 높이(Height): 루트에서 가장 먼 리프까지의 경로 길이
  - 차수(Degree): 노드가 가진 자식 노드의 수
  - 서브트리(Subtree): 트리 내의 부분 트리

- **트리의 순회 방법**:
  - **전위 순회(Preorder)**: 루트 → 왼쪽 서브트리 → 오른쪽 서브트리
  - **중위 순회(Inorder)**: 왼쪽 서브트리 → 루트 → 오른쪽 서브트리
  - **후위 순회(Postorder)**: 왼쪽 서브트리 → 오른쪽 서브트리 → 루트
  - **레벨 순서 순회(Level-order)**: 레벨별로 노드를 순회 (BFS와 유사)

### 이진 트리

- **정의**: 각 노드가 최대 2개의 자식을 가질 수 있는 트리
- **종류**:
  - **정 이진 트리(Full Binary Tree)**: 모든 노드가 0개 또는 2개의 자식을 가짐
  - **완전 이진 트리(Complete Binary Tree)**: 마지막 레벨을 제외한 모든 레벨이 완전히 채워져 있고, 마지막 레벨은 왼쪽부터 채워짐
  - **포화 이진 트리(Perfect Binary Tree)**: 모든 내부 노드가 2개의 자식을 가지고, 모든 리프 노드가 같은 레벨에 있음
  - **편향 이진 트리(Skewed Binary Tree)**: 한쪽으로만 노드가 연결된 트리

### 이진 탐색 트리(BST)

- **정의**: 왼쪽 서브트리의 모든 노드는 루트보다 작고, 오른쪽 서브트리의 모든 노드는 루트보다 큰 이진 트리
- **연산의 시간 복잡도**:
  - 접근(Access): O(log n) (평균), O(n) (최악, 편향된 경우)
  - 검색(Search): O(log n) (평균), O(n) (최악)
  - 삽입(Insert): O(log n) (평균), O(n) (최악)
  - 삭제(Delete): O(log n) (평균), O(n) (최악)

### 균형 이진 탐색 트리

- **정의**: 트리의 높이를 최소화하여 연산의 효율성을 보장하는 이진 탐색 트리
- **종류**:
  - **AVL 트리**: 노드의 왼쪽과 오른쪽 서브트리의 높이 차이가 최대 1인 이진 탐색 트리
  - **레드-블랙 트리(RB Tree)**: 노드에 색(레드/블랙)을 부여하여 균형을 유지하는 이진 탐색 트리
    - 모든 노드는 빨간색 또는 검은색
    - 루트 노드는 검은색
    - 모든 리프 노드(NIL)는 검은색
    - 빨간색 노드의 자식은 모두 검은색
    - 임의의 노드에서 그 노드의 모든 리프 노드까지의 경로에 있는 검은색 노드 수는 같음

### 힙(Heap)

- **정의**: 완전 이진 트리 기반의 자료구조, 부모 노드와 자식 노드 간의 대소 관계가 있음
- **종류**:
  - **최대 힙(Max Heap)**: 부모 노드의 값이 자식 노드보다 크거나 같음
  - **최소 힙(Min Heap)**: 부모 노드의 값이 자식 노드보다 작거나 같음

- **연산의 시간 복잡도**:
  - 삽입(Insert): O(log n)
  - 삭제(Delete): O(log n)
  - 최대/최소값 조회: O(1)

- **활용 사례**: 우선순위 큐, 힙 정렬

### B-트리와 B+트리

- **B-트리**: 자식 노드가 여러 개 있을 수 있는 균형 트리, 디스크 기반 저장에 유리
  - 모든 리프 노드가 같은 레벨에 있음
  - 각 노드는 여러 개의 키와 자식 포인터를 가짐
  - 데이터베이스 인덱싱에 주로 사용

- **B+트리**: B-트리의 변형으로, 리프 노드에만 데이터를 저장
  - 모든 키가 리프 노드에 저장됨
  - 리프 노드들은 연결 리스트로 연결됨
  - 범위 검색에 효율적

## 6. 그래프

- **정의**: 정점(Vertex)과 간선(Edge)으로 구성된 비선형 자료구조
- **용어**:
  - 정점(Vertex): 그래프의 기본 단위(노드)
  - 간선(Edge): 정점을 연결하는 선
  - 인접(Adjacent): 두 정점이 간선으로 직접 연결된 상태
  - 경로(Path): 정점들의 연속된 시퀀스
  - 사이클(Cycle): 시작 정점과 끝 정점이 같은 경로

- **그래프의 종류**:
  - **방향 그래프(Directed Graph)**: 간선에 방향이 있는 그래프
  - **무방향 그래프(Undirected Graph)**: 간선에 방향이 없는 그래프
  - **가중치 그래프(Weighted Graph)**: 간선에 가중치가 있는 그래프
  - **연결 그래프(Connected Graph)**: 모든 정점 쌍 사이에 경로가 있는 그래프
  - **비연결 그래프(Disconnected Graph)**: 일부 정점 사이에 경로가 없는 그래프
  - **완전 그래프(Complete Graph)**: 모든 정점 쌍이 간선으로 연결된 그래프
  - **서브그래프(Subgraph)**: 원래 그래프의 일부 정점과 간선으로 구성된 그래프

- **그래프의 표현 방법**:
  - **인접 리스트(Adjacency List)**: 각 정점에 연결된 정점들을 리스트로 표현
    - 공간 복잡도: O(V + E) (V: 정점 수, E: 간선 수)
    - 두 정점 연결 여부 확인: O(degree(V))
    - 모든 간선 순회: O(V + E)

### 그래프 탐색 알고리즘

#### 깊이 우선 탐색(DFS, Depth-First Search)

- **정의**: 그래프에서 최대한 깊이 탐색하고 더 이상 갈 곳이 없을 때 되돌아가는 방식
- **구현 방법**:
  - 재귀 함수 사용
  - 스택 자료구조 사용
- **과정**:
  1. 시작 정점을 방문 처리
  2. 인접한 미방문 정점이 있으면 방문
  3. 더 이상 방문할 정점이 없으면 이전 정점으로 돌아감
  4. 모든 정점을 방문할 때까지 2-3 반복
- **시간 복잡도**: O(V + E)
- **활용 사례**: 경로 탐색, 사이클 감지, 위상 정렬

#### 너비 우선 탐색(BFS, Breadth-First Search)

- **정의**: 그래프에서 같은 레벨의 정점들을 모두 방문한 후 다음 레벨로 진행하는 방식
- **구현 방법**: 큐 자료구조 사용
- **과정**:
  1. 시작 정점을 큐에 넣고 방문 처리
  2. 큐에서 정점을 꺼내 인접한 미방문 정점을 모두 큐에 넣고 방문 처리
  3. 큐가 빌 때까지 2 반복
- **시간 복잡도**: O(V + E)
- **활용 사례**: 최단 경로 탐색(가중치가 없거나 같은 경우), 레벨 순서 탐색

### 최단 경로 알고리즘

#### 다익스트라 알고리즘(Dijkstra's Algorithm)

- **정의**: 하나의 시작 정점에서 다른 모든 정점까지의 최단 경로를 구하는 알고리즘
- **조건**: 간선의 가중치가 음수가 아닐 때 사용 가능
- **과정**:
  1. 시작 정점의 최단 거리를 0으로, 나머지 정점은 무한대로 초기화
  2. 방문하지 않은 정점 중 최단 거리가 가장 작은 정점 선택
  3. 선택한 정점의 인접 정점들에 대해 최단 거리 갱신
  4. 모든 정점을 방문할 때까지 2-3 반복
- **시간 복잡도**: O(V²) (인접 행렬 사용 시), O(E log V) (우선순위 큐 사용 시)
- **활용 사례**: 네트워크 라우팅, 지도 어플리케이션의 경로 찾기
