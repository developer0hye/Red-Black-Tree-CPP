# Red-Black Tree

Red-Black Tree 란 Balanced search tree 의 일종인 자료구조이다. 모든 자료구조 관련 서적에서 등장이 될 정도이니 Red-Black Tree 를 공부하지 않고서는 "나 자료구조 공부한 사람이오." 라고 할 수 없을 것 같다. 그러니 공부해보자.

## What is Red-Black Tree?

Red-Black Tree 는 Balanced search tree 라고 앞에서 설명했다.

Balanced search tree 는 n 개의 노드(=데이터)를 저장하는 search tree 가 있을 때, 해당 tree의 높이가 O(lg n) 이 보장되는 tree 를 의미한다. 그 예로는, AVL Tree, 2-3 Tree, 2-3-4 Tree, B-Tree, **Red-Black Tree** 등이 있다.

**높이가 O(lg n)으로 보장된다는 의미는 삽입과 삭제시에 요구되는 계산 복잡도 또한 O(lg n) 이하로 보장됨을 의미한다.**

### Red-Black Properties

Red-Black Tree 는 특이하게도 각 노드의 색상을 저장하기 위한 color field 를 가진다.

자세한 속성은 아래와 같다.
- 모든 노드의 색상은 red 또는 black 이다.
- root 노드와 모든 leaf 노드의 색상은 black 이다.
- 만약 어떤 노드의 색상이 red 라면, 해당 노드의 부모 색상은 black 이다.
- 어떤 노드 x 에서 descendant(x 의 자식 노드) 노드까지의 경로에는 동일한 수의 black 노드를 가진다.


## Applications

표준 C++ 라이브러리(Standard Template Library: STL) 에서 제공되는 자료구조인 map 과 set 이 Red-Black Tree 로 구현되어 있다.

