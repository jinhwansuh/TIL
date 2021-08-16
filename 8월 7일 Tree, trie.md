# Tree



![](https://images.velog.io/images/jins/post/9d09765e-efd9-46a5-9e3b-0efbe310c8d0/image.png)

[https://towardsdatascience.com/8-useful-tree-data-structures-worth-knowing-8532c7231e8c?gi=c7677fbea793]

#### 사용 : DOM, File system, 계층구조 etc...

<br>

## 특징



- 루트 노드(root node): 부모가 없는 최상위 노드
- 단말 노드(leaf node): 자식이 없는 노드
- 크기(size): 트리에 포함된 모든 노드의 개수
- 깊이(depth): 루트 노드로부터의 거리
- 높이(height): 깊이 중 최댓값
- 차수(degree): 각 노드의 간선 개수

![](https://images.velog.io/images/jins/post/b0acf3f2-bc5d-4b11-afd8-a0fd47b9d4fb/image.png)
[https://yonghyuc.wordpress.com/2019/06/30/binary-tree-inorder-traversal/]

**<u>이진 탐색 트리의 특징: 왼쪽 자식 노드 < 부모 노드 < 오른쪽 자식 노드</u>**
(자료구조 공부할 땐 이 특징을 잘 안지키는 것 같다.)


## 순회 방법


![](https://images.velog.io/images/jins/post/518a6f88-e825-4710-9437-b937f9e93a11/image.png)

- **전위 순회(pre-order traverse)**: 루트를 먼저 방문 
	- 2 -> 7 -> 2 -> 6 -> 5 -> 11 -> 5 -> 9 -> 4  (root, left, right)
    
- **중위 순회(in-order traverse)**: 왼쪽 자식을 방문한 뒤에 루트를 방문
	- 2 -> 7 -> 5 -> 6 -> 11 -> 2 -> 5 -> 9 -> 4  (left, root, right)
- **후위 순회(post-order traverse)**: 오른쪽 자식을 방문한 뒤에 루트를 방문
	- 2 -> 5 -> 11 -> 6 -> 7 -> 4 -> 9 -> 5 -> 2 (left, right, root)





# Trie

![](https://images.velog.io/images/jins/post/7a4700ac-70d1-40df-ac1a-b329316413fc/image.png)
[https://en.wikipedia.org/wiki/Trie]



#### 사용 : 자동완성, 사전 찾기 etc...

## 특징

- 자동완성, 사전찾기 등에 이용된다.
- 문자열 탐색에서 단순 비교보단 효율적으로 찾을 수 있다.
- 자식에 대한 링크를 전부 가지고 있어 => 저장공간 더 많이 사용한다.

## 구조
1. 루트는 비어있다.
2. 각 간선(링크)은 추가될 문자를 키로 가진다.
3. 각 정점은 이전 정점값 + 간선의키로 가진다.
4. 해시 테이블, 연결 리스트를 이용하여 구현가능하다.

