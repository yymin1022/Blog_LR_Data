[문제 바로가기](https://boj.kr/18186)

```c++
#include  <bits/stdc++.h>

using namespace std;

long long arr[1000001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, B, C;
    cin >> N >> B >> C;

    for(int i = 0; i < N; i++){
        cin >> arr[i];
    }

    long long ans = 0;
    for(int i = 0; i <  N; i++){
        if(arr[i + 1] <= arr[i + 2]){
            long long tmp3 = min(arr[i], min(arr[i + 1], arr[i + 2]));

            if(B < C){
                ans += tmp3 * B * 3;
            }else{
                ans += tmp3 * (B + C * 2);
            }

            arr[i] -= tmp3;
            arr[i + 1] -= tmp3;
            arr[i + 2] -= tmp3;

            long long tmp2 = min(arr[i], arr[i + 1]);

            if(B < C){
                ans += tmp2 * B * 2;
            }else{
                ans += tmp2 * (B + C);
            }

            arr[i] -= tmp2;
            arr[i + 1] -= tmp2;
        }else{
            long long tmp2 = min(arr[i], arr[i + 1] - arr[i + 2]);

            if(B < C){
                ans += tmp2 * B * 2;
            }else{
                ans += tmp2 * (B + C);
            }

            arr[i] -= tmp2;
            arr[i + 1] -= tmp2;

            long long tmp3 = min(arr[i], min(arr[i + 1], arr[i + 2]));

            if(B < C){
                ans += tmp3 * B * 3;
            }else{
                ans += tmp3 * (B + C * 2);
            }

            arr[i] -= tmp3;
            arr[i + 1] -= tmp3;
            arr[i + 2] -= tmp3;
        }

        ans += arr[i] * B;
    }

    cout << ans << "\n";

    return 0;
}
```