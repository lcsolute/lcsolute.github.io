# 链表的环

## 判断链表的环

在环形跑道中，速度不一致的两个人总是会相遇。

从链表头部开始，一个指针走两步，另一个一个指针走一步，那么如果有环，则会相遇。

```c
struct ListNode *fast = head, *low = head;

while (fast->next) {
    low = low->next;
    fast = fast->next;
    if (fast->next) {
        fast = fast->next;
    }
    if (fast == low) {
        break;
    }
}

if (fast->next) {
    print("有环");
} else {
    print("无环");
}
```

## 找到入环节点

```c
struct ListNode *fast = head, *low = head;

while (fast->Next) {
    low = low->next;
    fast = fast->next;
    if (fast->next) {
        fast = fast->next;
    }
    if (fast == head) {
        fast = head;
        while (fast != low) {
            fast = fast->next;
            low = low->next;
        }
        return fast;
    }
}
return NULL;
```