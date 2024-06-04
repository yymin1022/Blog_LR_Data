[문제 바로가기](https://boj.kr/12970)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    for(int A = 0; A <= N; A++){
        int B = N - A;
        if(A * B >= K){
            vector<int> cnt(B + 1, 0);
            for(int i = 0; i < A; i++){
                int tmp = min(B, K);
                cnt[tmp]++;
                K -= tmp;
            }

            for(int i = B; i >= 0; i--){
                for(int j = 0; j < cnt[i]; j++){
                    cout << "A";
                }

                if(i > 0){
                    cout << "B";
                }
            }

            return 0;
        }
    }

    cout << -1 << "\n";

    return 0;
}
```