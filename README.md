# 컴퓨터 과학 (Computer Science) 개요
- **정의**: 컴퓨터 과학은 컴퓨터, 알고리즘, 데이터 구조, 하드웨어와 소프트웨어가 작동하는 원리에 대해 연구하는 학문입니다.
- **왜 공부해야 할까?**
  - 문제 해결 능력과 비판적 사고 가능
  - 사회에 영향을 미치는 소프트웨어와 시스템 개발 가능
  - 인공지능(AI), 사이버 보안, 데이터 과학 등 다양한 분야의 기초적인 내용 학습


## 1, 자료구조
### 1-1 자료구조란?
#### 정의
자료구조는 데이터를 효율적으로 저장, 관리, 접근하기 위해 사용하는 구조적인 방법입니다. 이는 데이터를 어떻게 조직화하고 저장할 지에 대한 청사진을 제공합니다.
- **목적**:
  - 데이터를 **효율적으로 처리하여** 프로그램의 성능을 최적화합니다.
  - 메모리를 효과적으로 사용하여 불필요한 낭비를 줄입니다.
  - 문제를 해결할 떄 적합한 구조를 선택함으로써 실행 속도를 크게 개선할 수 있습니다.
- **분류**:
  - **선형 구조(Linear Data Structures)**:  
      데이터가 **연속적** 또는 **순차적**으로 배치되는 구조입니다.
    - 배열 (Array): 고정된 크기의 데이터 집합.
    - 연결 리스트 (Linked List): 포인터를 통해 요소를 연결하는 동적 구조.
    - 스택 (Stack): 후입선출 (LIFO) 방식으로 동작.
    - 큐 (Queue): 선입선출 (FIFO) 방식으로 동작.
  - **비선형 구조(Non-linear Data Structures)**:  
    데이터가 **계층적**이거나 **복잡한 관계**를 가지는 구조입니다.
    - 트리 (Tree): 계층 구조로 데이터를 구성.
    - 그래프 (Graph): 노드와 간선으로 데이터의 관계를 표현.
    - 힙 (Heap): 우선순위가 높은 데이터가 먼저 처리되는 구조.

### 1-2 시간복잡도
#### 정의
시간 복잡도는 알고리즘이 실행되는 데 걸리는 시간을 입력 크기와의 관계로 표현한 척도입니다. 이를 통해 알고리즘이 대규모 데이터에서 얼마나 효율적인지 평가할 수 있습니다.

### 1-3 공간복잡도
#### 정의
공간 복잡도는 알고리즘이 실행되는 동안 사용하는 메모리 공간의 입력 크기와의 관계로 나타낸 척도입니다. 이는 효율적인 메모리 사용과 관련이 있습니다.

### 1-4 빅오 표기법(Big-O Notation)
#### 정의
**빅오 표기법**은 알고리즘의 성능을 분석하고, 가장 **최악의 경우(Worst Case)**에서의 시간 또는 공간 복잡도를 나타내는 수학적 표기법입니다.
이는 입력 크기 (```N```)이 커질수록 알고리즘의 실행시간이 어떻게 변하는지 평가하기 위한 도구로 사용됩니다.
#### 주요 특징
- **최악의 경우를 가정**하여 알고리즘의 효율설을 분석
- 데이터 크기에 따라 알고리즘의 실행 시간 또는 메모리 사용량이 어떻게 변하는지 나타냄
- 정확한 실행 시간(초 단위)을 측정하는 대신, 입력 크ㄱ와 실행 시간 간의 관계를 표현

### 1-5 자료구조의 기본 연산
자료구조에서 핵심적인 연산은 다음과 같습니다:
1) **탐색(Srearch)**: 특정 데이터를 자료구조 내에서 찾는 과정입니다.
2) **삽입(Insert)**: 새로운 데이터를 자료구조에서 추가하는 과정입니다.
3) **삭제(Delete)**: 자료구조에서 특정 데이터를 제거하는 과정입니다.  

이러한 기본 연산은 각 자료구조마다 구현 방법과 효율성이 다르며, 특정 상황에 적합한 자료구조를 선택하는 데 중요한 요소입니다.

### 1-6 자료구조 
#### 1, 배열(Array)
- **정의**: 동일한 타입의 요소들이 연속적으로 메모리에 저장된 자료구조입니다.
- **특징**:
  인덱스를 통해 빠르게 접근 가능하지만, 크기가 고정되어 동적 크기 조정이 어려움.
- **기본 연산**:

```cpp
#include <iostream>
using namespace std;

int main() {
    // 배열 선언 및 초기화
    int arr[5] = {1, 2, 3, 4, 5};
    
    // 탐색: 특정 인덱스 접근 (O(1))
    cout << "3rd element: " << arr[2] << endl;
    
    // 삽입: 특정 위치에 값 변경 (O(1))
    arr[2] = 10;
    cout << "Updated 3rd element: " << arr[2] << endl;

    // 삭제: 특정 값을 0으로 초기화 (실제 삭제는 불가, O(1))
    arr[4] = 0;
    cout << "Deleted 5th element: " << arr[4] << endl;

    // 순차 탐색: 배열 전체 순회 (O(N))
    cout << "Array elements: ";
    for (int i = 0; i < 5; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}

```

#### 2, 연결 리스트(Linked List)
- **정의**: 각 노드가 데이터와 다음 노드에 대한 포인터를 포함하는 자료구조
- **특징**:
  삽입과 삭제가 용이하지만 탐색은 순차적으로 이루어져야 함.
- **기본 연산**:

```cpp
#include <iostream>
using namespace std;

// 노드 정의
struct Node {
    int data;
    Node* next;
};

// 연결 리스트 클래스
class LinkedList {
public:
    Node* head;

    LinkedList() { head = nullptr; }

    // 삽입 (O(1) - 시작 부분)
    void insert(int value) {
        Node* newNode = new Node();
        newNode->data = value;
        newNode->next = head;
        head = newNode;
    }

    // 삭제 (O(N) - 특정 값 삭제)
    void remove(int value) {
        Node* current = head;
        Node* previous = nullptr;
        while (current != nullptr && current->data != value) {
            previous = current;
            current = current->next;
        }
        if (current == nullptr) return; // 값이 없으면 종료
        if (previous == nullptr) { // 삭제할 노드가 head인 경우
            head = current->next;
        } else {
            previous->next = current->next;
        }
        delete current;
    }

    // 탐색 (O(N))
    bool search(int value) {
        Node* current = head;
        while (current != nullptr) {
            if (current->data == value) return true;
            current = current->next;
        }
        return false;
    }

    // 출력 (O(N))
    void display() {
        Node* current = head;
        while (current != nullptr) {
            cout << current->data << " ";
            current = current->next;
        }
        cout << endl;
    }
};

int main() {
    LinkedList list;
    list.insert(10);
    list.insert(20);
    list.insert(30);

    cout << "List after inserts: ";
    list.display();

    cout << "Search 20: " << (list.search(20) ? "Found" : "Not Found") << endl;

    list.remove(20);
    cout << "List after deleting 20: ";
    list.display();

    return 0;
}

```

#### 3, 스택(Stack)
- **정의**: 마지막에 삽입된 요소가 가장 먼저 삭제되는 **후입선출(LIFO)** 자료구조
- **특징**:
  배열이나 연결 리스트로 구현 가능
- **기본 코드**:

```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    stack<int> s;

    // 삽입 (Push) - O(1)
    s.push(10);
    s.push(20);
    s.push(30);

    // 탐색 (Top) - O(1)
    cout << "Top element: " << s.top() << endl;

    // 삭제 (Pop) - O(1)
    s.pop();
    cout << "Top after pop: " << s.top() << endl;

    // 출력
    cout << "Stack elements: ";
    while (!s.empty()) {
        cout << s.top() << " ";
        s.pop();
    }
    cout << endl;

    return 0;
}

```

#### 4, 큐(Queue)
- **정의**: 먼저 삽입된 요소가 가장 먼저 삭제되는 **선입선출(FIFO)** 자료구조
  - **특징**:
    배열,연결 리스트, 또는 C++ STL의 ```queue```를 사용
- **기본 코드**:

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> q;

    // 삽입 (Enqueue) - O(1)
    q.push(10);
    q.push(20);
    q.push(30);

    // 탐색 (Front) - O(1)
    cout << "Front element: " << q.front() << endl;

    // 삭제 (Dequeue) - O(1)
    q.pop();
    cout << "Front after dequeue: " << q.front() << endl;

    // 출력
    cout << "Queue elements: ";
    while (!q.empty()) {
        cout << q.front() << " ";
        q.pop();
    }
    cout << endl;

    return 0;
}

```

#### 5, 덱(Deque)
- **정의**: 양쪽 끝에서 삽입과 삭제가 모두 가능한 선형 자료구조입니다.
- **특징**:
  - 삽입과 삭제가 양쪽에서 모두 가능
  - 스탯과 큐의 기능을 모두 포함
- **기본 코드**:

```cpp
#include <iostream>
#include <deque>
using namespace std;

int main() {
    deque<int> dq;

    // 앞쪽에 삽입 (O(1))
    dq.push_front(10);
    dq.push_front(20);

    // 뒤쪽에 삽입 (O(1))
    dq.push_back(30);
    dq.push_back(40);

    // 탐색 (O(1))
    cout << "Front: " << dq.front() << endl;
    cout << "Back: " << dq.back() << endl;

    // 앞쪽에서 삭제 (O(1))
    dq.pop_front();

    // 뒤쪽에서 삭제 (O(1))
    dq.pop_back();

    // 출력
    cout << "Deque elements: ";
    for (int num : dq) {
        cout << num << " ";
    }
    cout << endl;

    return 0;
}

```


#### 6, 해시 테이블(Hash Table)
- **정의**: 키(Key)를 해시 함수로 변환하여 데이터를 저장하는 자료구조
- **특징**:
  C++에서는 STL의 ```unordered_map```을 사용하여 해시 테이블 구현 가능
- **기본 코드**:

```cpp
#include <iostream>
#include <unordered_map>
using namespace std;

int main() {
    unordered_map<string, int> hashTable;

    // 삽입 - O(1) 평균
    hashTable["apple"] = 10;
    hashTable["banana"] = 20;

    // 탐색 - O(1) 평균
    cout << "Value for 'apple': " << hashTable["apple"] << endl;

    // 삭제 - O(1) 평균
    hashTable.erase("apple");

    // 확인
    if (hashTable.find("apple") == hashTable.end())
        cout << "'apple' not found" << endl;

    return 0;
}

```

#### 7, 그래프(Graph)
- **정의**: **노드(정점,Vertex)**와 **간선(Edge)**으로 구성된 비선형 자료구조입니다.
- **특징**:
  - 간선의 방향성 여부에 따라 **무방향 그래프**와 **유방향 그래프**로 나뉨
  - 간선에 가중치가 있으면 **가중치 그래프**라고 함
- **기본 그래프 표현**:
  - **인접 행렬(Adjacency Matrix)**: 2차원 배열을 사용하여 그래프를 표현
  - **인접 리스트(Adjacency List)**: 각 정점의 연결된 정점을 리스트로 저장
- **기본 코드**:
1) DFS(깊이 우선 탐색):
```cpp
#include <iostream>
#include <vector>
using namespace std;

void dfs(int node, vector<vector<int>>& adjList, vector<bool>& visited) {
    visited[node] = true;
    cout << node << " ";
    for (int neighbor : adjList[node]) {
        if (!visited[neighbor]) {
            dfs(neighbor, adjList, visited);
        }
    }
}

int main() {
    int V = 5; // 정점 개수
    vector<vector<int>> adjList(V);
    vector<bool> visited(V, false);

    // 간선 추가
    adjList[0].push_back(1);
    adjList[0].push_back(2);
    adjList[1].push_back(3);
    adjList[2].push_back(4);

    cout << "DFS Traversal: ";
    dfs(0, adjList, visited);
    cout << endl;

    return 0;
}

```
2) BFS(넓이 우선 탐색):
```cpp
#include <iostream>
#include <vector>
#include <queue>
using namespace std;

void bfs(int start, vector<vector<int>>& adjList) {
    vector<bool> visited(adjList.size(), false);
    queue<int> q;

    visited[start] = true;
    q.push(start);

    while (!q.empty()) {
        int node = q.front();
        q.pop();
        cout << node << " ";

        for (int neighbor : adjList[node]) {
            if (!visited[neighbor]) {
                visited[neighbor] = true;
                q.push(neighbor);
            }
        }
    }
}

int main() {
    int V = 5; // 정점 개수
    vector<vector<int>> adjList(V);

    // 간선 추가
    adjList[0].push_back(1);
    adjList[0].push_back(2);
    adjList[1].push_back(3);
    adjList[2].push_back(4);

    cout << "BFS Traversal: ";
    bfs(0, adjList);
    cout << endl;

    return 0;
}

```

#### 8, 트리(Tree) - 이진 검색 트리(Binary Search Tree)
- **정의**: 각 노드가 최대 두 개의 자식을 가지며, 왼쪽 자식은 부모보다 작고 오늘쪽 자식은 부모보다 큽니다.
- **특징**:
  
- **기본 코드**:

```cpp
#include <iostream>
using namespace std;

// 노드 구조체
struct Node {
    int data;
    Node* left;
    Node* right;

    Node(int value) {
        data = value;
        left = right = nullptr;
    }
};

// 삽입 함수
Node* insert(Node* root, int value) {
    if (root == nullptr) return new Node(value);
    if (value < root->data) root->left = insert(root->left, value);
    else root->right = insert(root->right, value);
    return root;
}

// 탐색 함수
bool search(Node* root, int value) {
    if (root == nullptr) return false;
    if (root->data == value) return true;
    if (value < root->data) return search(root->left, value);
    return search(root->right, value);
}

// 중위 순회
void inOrder(Node* root) {
    if (root == nullptr) return;
    inOrder(root->left);
    cout << root->data << " ";
    inOrder(root->right);
}

int main() {
    Node* root = nullptr;
    root = insert(root, 50);
    insert(root, 30);
    insert(root, 70);
    insert(root, 20);
    insert(root, 40);

    cout << "In-order traversal: ";
    inOrder(root);
    cout << endl;

    cout << "Search 30: " << (search(root, 30) ? "Found" : "Not Found") << endl;

    return 0;
}

```

#### 9, 우선순위 큐(Priority Queue)
- **정의**: 각 요소가 우선순위를 가지며, **가장 높은 우선순위를 가진 요소가** 가장 먼저 처리되는 자료구조입니다.
- **특징**:
  - 일반 큐는 FIFO 방식이지만, 우선순위 큐는 우선순위에 따라 요소를 처리
  - 내부적으로 힙(Heap) 자료구조를 사용하여 구현
- **기본 코드**:  
C++ 구현: C++의 priority_queue는 기본적으로 최대 힙으로 동작 (가장 큰 값이 우선).
```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    // 최대 힙 (기본)
    priority_queue<int> maxHeap;

    maxHeap.push(10);
    maxHeap.push(30);
    maxHeap.push(20);

    cout << "Max-Heap elements: ";
    while (!maxHeap.empty()) {
        cout << maxHeap.top() << " "; // 최대값 출력
        maxHeap.pop();
    }
    cout << endl;

    // 최소 힙
    priority_queue<int, vector<int>, greater<int>> minHeap;

    minHeap.push(10);
    minHeap.push(30);
    minHeap.push(20);

    cout << "Min-Heap elements: ";
    while (!minHeap.empty()) {
        cout << minHeap.top() << " "; // 최소값 출력
        minHeap.pop();
    }
    cout << endl;

    return 0;
}

```

---
## 2, 운영체제
### 2-1 운영체제란?
운영체제는 컴퓨터의 자원을 관리하고, 프로그램에 대한 지원을 하는 시스템 SW

Application
CPU
Device
OS
Memory

시스템 콜

User Mode
Kernel Mode

Dual Mode

Kernel : 시스템 소프트웨어

인터럽트

프로그램 : 프로그래밍 언어를 통해서 만들어진 결과물

프로세스

언어의 분류
컴파일 과정
인터프리터 언어

아키텍쳐

컴파일러 
=> 컴파일 언어 -> 목적 프로그램
링커
=> 목적 프로그램들 => 실행 프로그램
.dll file

### 2-2 프로그램이 되는 과정
java
자바 가상 환경

javaScript
가상 환경


프로그램 -> 프로세스
로더 : 보조기억장치로부터 주기억장치에 프로그램을 적재하는 시스템 SW

모든 프로세스는 부모-자식 간의 트리 형태를 가짐
새로운 프로세스 생성은 fork() -> exec() 시스템 콜을 호출하는 방식

### 2-3 프로세스와 스레드
프로세스란?
프로그램이 메모리에 올라와 실행 가능한 상태가 되는 것

프로세스의 메모리 구조
- Text(Code) 영역 : 실행중인 프로그램이 포함되는 영역
- Data 영역 : 전역 변수, 정적변수 등이 저장됨, 컴파일때 크기가 정해짐
- Heap 영역 : 동적으로 할당되는 메모리 영역
- Stack 영역 : 함수 호출 값들이 저장되는 영역

콜 스탯
각 함수 내의 변수 정보도 함께 저장된다.

PCB(Process Control Block) 프로세스의 정보를 담은 일련의 저장공간  
Pointer : Process State  
Process Number(ID)  
Program Counter  
Registers  
Memory limits  
List of open files  

스레드
컴퓨터에서 작업을 수행하는 단위

프로세스와 스레드의 관계
프로세스 : 자원을 할당 받는 단위
스레드 : 작업을 수행하는 단위

스레드의 주소공간

CPU는 한번에 하나의 작업만
동시성 : 한 번에 여러 프로그램이 돌아가는 것 처럼 보이게 하는 것
병렬성 : 한 번에 여러 프로그램을 돌리는 것

스래드는 2가지가 있다
코어/스레드의 스레드든 CPU의 코어와 다는 논리적인 코어의 수
프로세스/스레드의 스레드는 작업을 수행하는 단위

### 2-4 프로세스 동기화
하나의 작업을 어떻게 나누어서 수행할까?
멀티 프로세싱 :  
멀티 스레딩 : 

성능-> 멀티 스레딩이 멀티 프로세싱보다 가볍다
안정성 -> 멀티 스레딩보다 멀티 프로세싱이 훨신 안정적이다.

Race Condition
타이밍에 따라 결과가 다르게 나올 수 있는 지점

Locking Algorithm
특정 자원이나, 진입점에 대해 잠금을 걸어버리는 메커니즘
=> Locking은 실행을 하고 나면 반드시 Locking 을 해제해야 한다.

Mutex : Mutual Exclustion의 약자로, 락의 소유권을 갖는 방식
Samaphore : 카운트 방식의 Locking Algorithm, 중앙에서 Lock의 소유권을 관리한다.

CAS
비교하고, 교환하는 코드를 한 번에 처리하는 방식
Atomic

### 2-5 프로세스 스케줄링

어떤 방식으로 동시성을 보장할 수 있는가?
스케줄링 알고리즘 : 
여러 프로세스를 어떤 방식으로 CPU에 할당할지 결정하는 알고리즘  
-> 대기시간 단축, 선택되지 않는 스레드가 없어야 한다.

FCFS(First Come, First Served)
먼저 들어온 프로세스부터 처리  
-> 대기시간이 길어질 수밖에 없다  
-> 우선순위가 적용되지 않는다.  

SJF(Shortest Job First)
가장 남은 시간이 잛은 Job을 우선적으로 처리  
-> 가장 이상적이지만 실현 불가  
-> 기존 기록을 확인 => 예상시간을 측정  

Preemtive VS Non-Preemtive
새로운 Job이 들어왔을 때, 수행중인 기존 Job을 빼앗을 수 있는가?

Priority Scheduling
프로세스에 우선순위를 지정하여, 그 순서대로 스케줄링
-> Aging 문제 : 우선순위가 낮은 프로세스는 수행되지 않을 수 있다.
-> 그래서 우선순위가 낮아서 실행되지 않는 프로세스는 일정 시간이 지나면 우선수위를 높힌다.

Round Robin(RR)
모든 프로세스 마다 동일한 시간 간격(Time Quantum)을 부여하는 방식

Multi-level Queue
프로세스를 우선순위에 따라 나누고, 각 층마다 서로 다른 알고리즘 사용

Multi-level Feedback Queue  
Multi-level Queue + Aging

### 2-6 캐시 메모리
램과 하드디스크

메모리의 계층성
메모리를 필요에 따라 여러 종류로 분리한 것
=> 자주 접근

캐시 메모리
CPU에 포함된 작은 메모리로, 접근 속도가 매우 빠름
한 번 접근한 값은 캐시 메모리에 저장되므로, 반복 접근 시 매우 빠름
-> Cache Miss(최초 접근)
-> Cache Hit(2회차 이상)
캐시의 크기는 작기 떄문에, 모든 데이터가 들어가지 못함

캐시 지역성
캐시의 효울을 위해선, 시간적/공간적으로 인접한 데이터 접근을 해야 함

### 2-7 메모리 관리

프로그램 쪼개서 밀어넣기

세그먼트 : 프로세스 주소공간에 맞춰서 프로세스를 분리하는 방식  
페이징 : 똑같은 크기의 "페이지"로 공간을 분리하는 방법  
-> 단편화의 단점 -> 내부 단편화, 외부 단편화  


Demanding Paging
프로그램 중에서 필요한 부분만 사용한다.

가상 메모리
프로그램의 실행중인 부분만 메모리에 적재하는 방식
Frame : 실제 램 공간 분할

페이지 테이블
pid : p : d
p => 몇번 페이지
d => 어느 위치

## 3. 네트워크
### 3-1 HTTP
HTTP란? 
Hyper Text Transfer Protocol
웹에서 파일을 주고 받기 위한 

Protocol
통신 방식에 대한 일종의 규약(어떤 방식으로 통신을 할 것인가?)
HTTP : Hyper Text Transfer Protocol
FTP : File Transfer Protocol
IP : Internet Protocol

### 3-2 OSI 7계층

OSI 7계층 : 네트워크 통신을 7개의 레이어로 나눈 것
HTTP Header

OSI 7계층 - 캡슐화

OSI 7계층 - 물리 계층
데이터의 물리적 연결(전기 신호)의 전송을 관리

OSI 7계층 - 데이터 링크 계층
네트워크 기기 간 데이터 전송, 오류 검출 및 제어 처리
MAC(주소) : 각 기기에 할당된 주소

OSI 7계층 - 네트워크 계층 
데이터의 전송 경로를 결정해주는 역할을 하는 계층
IP 주소

IP 주소 vs MAX 주소
IP 주소 : 상대적이며, 똑같은 기기에서도 다른 IP가 가능하다.
MAC 주소 : 각 기기에 귀속된 주소로, 변경이 불가능하다.

OSI 7계층 - 전송 계층
데이터를 신뢰성 있게 전송할 수 있도록 돕는 계층 + 프로세스 단위로 통신이 가능하다.
TCP vs UDP
IP Address VS Port Number
Port Number : 프로세스 포트 번호

OSI 7계층 - 응용 계층
전송 받은 데이터를 활용해서, 특정한 작업을 수행하는 계층

### 3-3 TCP vs UDP
전송 계층 - TCP
연결 지향적 전송 계층 프로토콜로, 안정적인 통신을 위한 기능을 제공
TCP - 3 Way Handshake
TCP - 4 Way Handshake
TCP - Sequence Number

TCP - HTTP
주로 HTML 문서를 주고받는 데에 쓰인다. 주로 TCP를 사용한다.

HTTP Persistent Connection
HTTP Stateless

TCP의 단점
기능이 몹시, 몹시 많다! -> 느리다

전송 계층 - UDP
비연결 지향적 전송 계층 프로토콜로, 특별한 추가 기능을 제공하지 않음
TCP에 비해 엄청나게 가볍다!


### 3-4 인터넷을 타고 떠나는 여행

단골 질문 
주소창에 www.naver.com을 쳤을 때, 네트워크에서 발생하는 일을 최대한 자세히 설명하세요

1) 인터넷에 연결하기 : IP 주소를 할당받는다.  
유동 IP, 고정 IP => 어떻게 IP 주소를 받을까?
=> DHCP(Dynamic Host Configuration Protocol) IP 할당 받기위한 절차 
-> DHCP Discover => BroadCast => IP 주소를 받기 위해 주변에 모든 곳에 요청을 보낸다.
=> 우리가 쓰는 인터넷의 95%는 유동 IP이다.(IPv6)  
=> 고정 IP를 발급 받아서, 계속 사용한다.
2) 목적지 IP 주소를 찾는다.
도메인에서 IP로
도메인 : IP에 대한 별칭으로, 사람이 기억하기 쉽도록 만든 것
DNS : Domain Name Server - 도메인에 대한 정보를 갖고 있는 서버들
도메인 체계 : 
DNS Query 
1, 로컬 저장 데이터를 확인한다.(DNS Cache,Host File)
2, 최상위 도메인부터 시작하여, 상위에서 하위로 내려가며 주소를 구한다.
3) 네트워크에 최적의 경로를 찾아서 연결한다.
라우터 : 패킷을 추출하여, 그 위치에 대한 최적의 경로를 지정하여 전달하는 장치
최적의 경로를 찾는 법
Routing Table
Subnet : IP 주소에서 네트워크 영역을 부분적으로 나눈 네트워크
이동할 때마다 캡슐화
HTTP는 TCP니까
HTTP Handshake - 3 Way Handshake
HTTPS - HTTP-Secure
HTTP는 데이터 전송시 암호화 안하고 원본 그래도 전송
HTTPS는 데이터 전송시 암호화해서 전송
어떻게 암호화?

HTTPS (7 Way) Handshake(SSL/TLS)

HTTP Header 살펴보기 => Web Server로 간다.
method    path                                       protocol
GET     /tutorials/other/top-20-mysql-best-practices/HTTP 1.1

Web Application Server

Web Server

                    |- WAS 서버(동적 데이터)
Client - Web Server -- WAS 서버(동적 데이터)
                    |- HTML,Image,CSS,JS 정적 데이터

Web Server(HTTP Daemon)의 역할
1, 요청을 파싱하여, 도메인/세부 경로/메서드로 분할
2, 서버가 해당 매서드에 대한 요청을 받을 수 있는지 확인
3, 요청에 대한 자원 처리

만약 서버의 규모가 크다면?
1, 분산 서버

Load Balancer
사용자의 요청을 여러 서버에 분산하는 도구
DNS Query를 통해 얻는 IP는 어디를 가리키고 있는가? => Load Balancer를 가리키고 있을 확률이 높다
Round Robin : 들어오는 순서대로 돌아가면서 배분
Least Connection : 현재 연결의 수가 가장 적은 서버로 전송

L4/L7 Load Balancer

L7 Load Balancer
HTTP 헤더/쿠키 등의 정보를 활용하거나
패킷의 내용을 확인하고 그 내용을 기반으로 서버 분배 가능

HTML, CSS,JS - 파싱
- DOM : 트리 구조를 가지고 있다.
- DOM Tree
(1) DOM Tree 생성
(2) 스타일 규칙 생성
(3) 렌더 트리 생성
(4) 레이아웃(-> 리플로우)
(5) 페인트(-> 리페인트)


### 3-5 CORS

CORS Policy?
Cross-Origin Resource Sharing - 교차 출처 리소스 공유
Cross-Site Request Forgery - 사이트 간 요청 위조
- 1 CSRF 스크립트가 포함된 게시물 등록
- 2 CSRF 스크립트가 포함된 게시물 열람
- 3 CSRF 스크립트가 포함된 게시물 응담
- 4 CSRF 스크리트 실행(사용자 권한)

dreamhack.io/wargame/challenges/26

Same Origin Polocy - 같은 Origin이 아니면 전송을 거부한다. 

Access-Control-Allow-Origin이 붙은 경우에 한 해, 예외적으로 가능하다.

### 3-6 SQL Injection

1 SELECT * FROM Users WHERE id = 'INPUT1' AND password = 'INPUT2'

