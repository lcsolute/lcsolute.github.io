---
title: '深入理解计算机系统'
date: '2023-06-09'
---

## 02 信息的表示和处理

```c
#include <stdio.h>

typedef unsigned char * byte_pointer;

void show_bytes(byte_pointer start, size_t len) {
    for (size_t i = 0; i < len; i++)
        printf("%.2x", start[i]);
    print("\n");
}

void show_int(int x) {
    show_bytes((byte_pointer) &x, sizeof(int));
}

void show_float(float x) {
    show_bytes((byte_pointer) &x, sizeof(float));
}

void show_pointer(void * x) {
    show_bytes((byte_pointer) &x, sizeof(void *));
}
```

测试代码

```c
int main() {
    int x = 0x123456;
    show_int(x);
}
```

运行结果为：`123456` 或 `563421`
