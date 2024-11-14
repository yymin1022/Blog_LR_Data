[문제 바로가기](https://boj.kr/32369)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, A, B;
    cin >> N >> A >> B;

    int resA = 1;
    int resB = 1;
    for(int i = 0; i < N; i++){
        resA += A;
        resB += B;

        if(resA == resB){
            resB--;
        }else if(resA < resB){
            swap(resA, resB);
        }
    }

    cout << resA << " ";
    cout << resB << "\n";

    return 0;
}

```
