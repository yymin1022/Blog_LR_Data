[문제 바로가기](https://boj.kr/1038)

```c++
#include <bits/stdc++.h>

using namespace std;

vector<long> arr;

void calc(long num, int len){
    if(len > 10){
        return;
    }

    arr.push_back(num);

    for(int i = 0; i < 10; i++){
        if(num % 10 > i){
            calc((num * 10) + i, len + 1);
        }
    }
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    if(N > 1022){
        cout << -1 << "\n";
        return 0;
    }

    if(N < 1){
        cout << N << "\n";
        return 0;
    }

    for(int i = 0; i < 10; i++){
        calc(i, 1);
    }

    sort(arr.begin(), arr.end());

    cout << arr[N] << "\n";

    return 0;
}
```