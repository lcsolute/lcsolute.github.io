---
title: '二分查找题型总结'
date: '2023-06-01'
---

## 二分答案转变成判定

本质：

解空间具有一种特殊的单调性 ——— 单调分段函数

这种类型的题目有两种情况：

1. 最大化最小值

模版：

```cpp
while (l < r) {
    int mid = (l + r + 1) >> 1;
    if (valid(mid)) l = mid;
    else r = mid - 1;
}
```

[LeetCode 2517. 礼盒的最大甜蜜度](https://leetcode.cn/problems/maximum-tastiness-of-candy-basket/description/)

2. 最小化最大值

模板：

```cpp
while (l < r) {
    int mid = (l + r) >> 1;
    if (valid(mid)) r = mid;
    else l = mid + 1;
}
```
[2439. 最小化数组中的最大值](https://leetcode.cn/problems/minimize-maximum-of-array/)

判定（vaild函数）：

一般使用贪心来计算