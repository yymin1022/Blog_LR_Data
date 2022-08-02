[문제 바로가기](https://boj.kr/4673)

```c++
#include <bits/stdc++.h>

using namespace std;

int nums[10001] = {};

int d(int n){
    return n / 1000 + n % 1000 / 100 + n % 100 / 10 + n % 10 + n;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    for(int i = 1; i < 10000; i++){
        int num = d(i);
        if(num < 10000){
            nums[num] = 1;
        }
    }

    for(int i = 1; i < 10000; i++){
        if(nums[i] != 1){
            cout << i << "\n";
        }
    }
}```