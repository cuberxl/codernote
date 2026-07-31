# Page 9 
### 动态链表结构

```cpp
struct Node//单链表结构
{
	int val;        // 该结构的值
	Node *next;     // 该结构的下一个结点
	Node(int x): val(x), next(NULL) {} // 构造函数
};
```