# Red-Black Tree

Red-Black Tree 란 Balanced search tree 의 일종인 자료구조이다. 모든 자료구조 관련 서적에서 등장이 될 정도이니 Red-Black Tree 를 공부하지 않고서는 "나 자료구조 공부한 사람이오." 라고 할 수 없을 것 같다. 그러니 공부해보자.

## What is Red-Black Tree?

Red-Black Tree 는 Balanced search tree 이며, 그중에서도 각 노드의 자식 노드가 최대 2인 트리를 의미한다.

Balanced search tree 는 n 개의 노드(=데이터)를 저장하는 search tree 가 있을 때, 해당 tree의 높이가 O(lg n) 이 보장되는 tree 를 의미한다. 그 예로는, AVL Tree, 2-3 Tree, 2-3-4 Tree, B-Tree, **Red-Black Tree** 등이 있다.

**높이가 O(lg n)으로 보장된다는 의미는 삽입과 삭제시에 요구되는 계산 복잡도 또한 O(lg n) 이하로 보장됨을 의미한다.**

## Why is it important that a binary tree be balanced?

아래와 같은 Binary tree 가 있다고 생각해보자. 이렇게 한 쪽으로 치우친 트리(모든 노드의 자식 노드 수가 1인 노드)를 우아한 전문용어로 Skewed tree 라고한다.

```
  A
   \
    B
     \
      C
       \
        D
         \
          E
```

어떤 Binary Tree 가 아주 재수없게도 Skewed Tree 형태로 자료를 저장하는 경우 Tree 의 기본적인 작업(operation)에 필요한 계산복잡도는 O(n) (worst case) 이 되어 Binary Tree 를 쓰는 이점이 사라지게된다. 따라서 Tree 가 Skewed Tree 가 되지 않도록 Tree 의 높이를 O(lg n) 로 유지 시켜주는 작업은 Binary Tree 를 효율적으로 다루기 위해서는 필수적인 작업이다.

### Red-Black Properties

Red-Black Tree 는 각 노드의 색상(red or black)을 저장하기 위한 color field 를 가진다.

자세한 특징은 아래와 같다.
- 1. 모든 노드의 색상은 red 또는 black 이다.
- 2. root 노드와 모든 leaf 노드의 색상은 black 이다.
- 3. 만약 어떤 노드의 색상이 red 라면, 해당 노드의 부모 색상은 black 이다.
- 4. 색상이 red 인 노드의 자식 노드는 black 노드이다. = red 노드가 연달아서 올 수 없다.
- 5. 어떤 노드 x 에서 descendant(x 의 자식 노드이자 leaf 인 노드) 노드까지의 경로에는 동일한 수의 black 노드가 존재한다.

Property 1~4 까지만 보면 기존 Binary Search Tree 에 색상 조건만 추가해주면 될 것 같다. 문제는 Property 5. 어떻게 구현해야 5번 조건을 만족할까?? 아마 가장 중요한 특징은 5. 인 것 같다.

아무튼, 위의 5 가지 특징으로 인하여 Red-Black Tree 의 높이는 O(lg n) 으로 바운드된다.

## Applications

표준 C++ 라이브러리(Standard Template Library: STL) 에서 제공되는 자료구조인 map 과 set 이 Red-Black Tree 로 구현되어 있다.

무려 **표준 라이브러리에 구현**되어있다니... 그 필요성이 느껴지며 공부를 해야겠다는 마음이 생길 수 밖에 없다.

