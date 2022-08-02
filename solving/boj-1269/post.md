[문제 바로가기](https://boj.kr/1269)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    set<int> A;
    for(int i = 0; i < N; i++){
        int temp;
        cin >> temp;
        A.insert(temp);
    }

    set<int> B;
    for(int i = 0; i < M; i++){
        int temp;
        cin >> temp;
        B.insert(temp);
    }

    int count = 0;
    for(auto cur = A.begin(); cur != A.end(); cur++){
        if(B.find(*cur) == B.end()){
            count++;
        }
    }
    for(auto cur = B.begin(); cur != B.end(); cur++){
        if(A.find(*cur) == A.end()){
            count++;
        }
    }

    cout << count << "\n";

    return 0;
}
```