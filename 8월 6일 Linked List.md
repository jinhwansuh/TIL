![](https://images.velog.io/images/jins/post/2c852573-f034-4a34-ab8b-2b5c82e7e15a/image.png)
[https://en.wikipedia.org/wiki/Linked_list]

# Linked list를 왜쓰는가?

<br><br>

우리에겐 [1,2,3,4,5] 같은 배열(Array)이 있다.

배열에는 물론 push()와 pop()같은 O(1)을 가진 stack의 개념을 사용할수 있지만, 배열안에 값을 넣고 빼고 할때 시간복잡도가 올라간다.
<br>




## Array vs Linked List
> 아래 표에 나타난 insert와 delete는 중간에 값을 insert하고 delete 하는 동시에 배열에 빈 공간이 없게 순서를 다시 정렬하는 작업을 의미한다.


| Big O       | find(index를 알때) | find(index를 모를때) | Insert | Delete |
| ----------- | ------------------ | -------------------- | ------ | ------ |
| Array       | O(1)               | O(n)                 | O(n)   | O(n)   |
| Linked List | O(1)               | O(n)                 | O(1)   | O(1)   |




**추가와 삭제를 반복적으로 하는 작업에 있어 Linked List가 훨씬 빠르다.**


#### 구현코드


```
class Node {
    constructor(value) {
        this.value = value;
        this.next = null;
    }
}

class SinglyLinked{
    constructor() {
        this.head = null;
        this.tail = null;
    }

    find(value) {
        let currNode = this.head;
        while (currNode.value !== value){
            currNode = currNode.next;
        }
        
        return currNode;
    }
    
    insert(node, newValue) {
        const newNode = new Node(newValue);
        newValue.next = node.next;
        node.next = newNode;
    }

    append(newValue) {
        const newNode = new Node(newValue);
        if (this.head === null) {
            this.head = newNode;
            this.tail = newNode;
        } else {
            this.tail.next = newNode;
            this.tail = newNode;
        }
    }
    remove(value) {
        let preNode = this.head;
        while (preNode.next.value !== value) {
            preNode = preNode.next;
        }

        if (preNode.next !== null) {
            preNode.next = preNode.next.next;
        }
    }


    display() {
        let currNode = this.head;
        let displayString = "["
        while (currNode !== null) {
            displayString += `${currNode.value}, `;
            currNode = currNode.next;
        }
        displayString = displayString.substr(0, displayString.length -2);
        displayString += "]";
        console.log(displayString)
    }
}
```


### 그렇다고 무조건 배열을 쓰지 말라는 것이 아니다. 


대략적인 시간복잡도를 예상하고 상황에 맞는 방법을 쓰면 된다. :)