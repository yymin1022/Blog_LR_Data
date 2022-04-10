[문제 바로가기](https://boj.kr/15596)

```c++
#include <vector>
long long sum(std::vector<int> &a) {
	long long ans = 0;
    
    for(int i = 0; i < a.size(); i++){
        ans += a[i];
    }
    
	return ans;
}
```