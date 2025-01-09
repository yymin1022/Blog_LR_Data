[문제 바로가기](https://boj.kr/15738)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K, M;
    cin >> N >> K >> M;

    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
    }

    int ans = K;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;

        if(input > 0){
            if(ans <= input){
                int left = 1;
                int right = input;
                int mid = (left + right) / 2;

                if(input % 2){
                    if(ans < mid){
                        ans = (mid - ans) + mid;
                    }else if(ans > mid){
                        ans = mid - (ans - mid);
                    }
                }else{
                    if(ans <= mid){
                        ans = (mid - ans) + mid + 1;
                    }else if(ans > mid){
                        ans = mid - (ans - mid) + 1;
                    }
                }
            }
        }else{
            if(ans >= N + input + 1){
                int left = N + input + 1;
                int right = N;
                int mid = (left + right) / 2;

                if((-input) % 2){
                    if(ans < mid){
                        ans = (mid - ans) + mid;
                    }else if(ans > mid){
                        ans = mid - (ans - mid);
                    }
                }else{
                    if(ans <= mid){
                        ans = (mid - ans) + mid + 1;
                    }else if(ans > mid){
                        ans = mid - (ans - mid) + 1;
                    }
                }
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```