[문제 바로가기](https://boj.kr/18185)

```c++
#include  <bits/stdc++.h>

using namespace std;

int arr[10001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        cin >> arr[i];
    }

    int ans = 0;
    for(int i = 0; i <  N; i++){
        if(arr[i + 1] <= arr[i + 2]){
            int tmp3 = min(arr[i], min(arr[i + 1], arr[i + 2]));
            ans += tmp3 * 7;
            arr[i] -= tmp3;
            arr[i + 1] -= tmp3;
            arr[i + 2] -= tmp3;

            int tmp2 = min(arr[i], arr[i + 1]);
            ans += tmp2 * 5;
            arr[i] -= tmp2;
            arr[i + 1] -= tmp2;
        }else{
            int tmp2 = min(arr[i], arr[i + 1] - arr[i + 2]);
            ans += tmp2 * 5;
            arr[i] -= tmp2;
            arr[i + 1] -= tmp2;

            int tmp3 = min(arr[i], min(arr[i + 1], arr[i + 2]));
            ans += tmp3 * 7;
            arr[i] -= tmp3;
            arr[i + 1] -= tmp3;
            arr[i + 2] -= tmp3;
        }

        ans += arr[i] * 3;
    }

    cout << ans << "\n";

    return 0;
}
```