[문제 바로가기](https://boj.kr/29891)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> A, B;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(input > 0){
            A.push_back(input);
        }else{
            B.push_back(input * -1);
        }
    }

    sort(A.begin(), A.end(), greater<int>());
    sort(B.begin(), B.end(), greater<int>());

    long long ans = 0;
    for(int i = 0; i < A.size(); i += K){
        ans += A[i] * 2;
    }

    for(int i = 0; i < B.size(); i += K){
        ans += B[i] * 2;
    }

    cout << ans << "\n";

    return 0;
}
```