[문제 바로가기](https://boj.kr/16455)

```c++
#include <bits/stdc++.h>

int kth(std::vector<int> &a, int k) {
    nth_element(a.begin(), a.begin() + k - 1, a.end());
    return a[k - 1];
}
```