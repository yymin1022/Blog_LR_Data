[문제 바로가기](https://boj.kr/25379)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N;
    cin >> N;

    vector<long long> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    long long cntA = 0;
    long long cntB = 0;
    long long tmpA = 0;
    long long tmpB = 0;
    for(int i = 0; i < N; i++){
        if((arr[i] % 2)){
            tmpB++;
            cntA += tmpA;
        }else{
            tmpA++;
            cntB += tmpB;
        }
    }

    cout << min(cntA, cntB);

    return 0;
}
```