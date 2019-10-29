### 순회 (Traversal)

------

> 탐색 연산이 조건을 만족하는 노드를 찾을 경우 작업을 종료하는 반면, 순회는 트리의 모든 노드를 방문하면서 각 노드에 대해 작업을 수행하는 것을 말한다.
>
> 트리에서 순회는 크게 세 가지 방법이 있으며, 각 방법에 따라 방문하는 순서가 다르다. 세 가지 방법은 다음과 같다.



#### 순회의 방법

> 노드와 자식 노드의 방문 순서에 따라 나뉜다. 단, 모든 경우에 대해서 자식 노드는 오른쪽 노드보다 왼쪽 노드를 먼저 방문한다. 각 방법을 구현하는 가장 간단한 방법은 재귀호출을 사용하는 방법이다.

##### 전위 순회 (Pre-order Traversal)

> 노드 > 왼쪽 자식 노드 > 오른쪽 자식 노드의 순으로 방문하는 방법을 말한다. 노드를 가장 먼저 방문하므로 전위 순회이다.

##### 중위 순회 (In-order Traversal)

> 왼쪽 자식 노드 > 노드 > 오른쪽 자식 노드의 순으로 방문하는 방법을 말한다. 노드를 중간에 방문하므로 중위 순회이다.

##### 후위 순회 (Post-order Traversal)

> 왼쪽 자식 노드 > 오른쪽 자식 노드 > 노드의 순으로 방문하는 방법을 말한다. 노드를 마지막에 방문하므로 후위 순회이다.
