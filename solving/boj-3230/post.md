[문제 바로가기](https://boj.kr/3230)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> arr(101, 0);
    for(int i = 1; i <= N; i++){
        int rank;
        cin >> rank;

        if(arr[rank] != 0 && i > 1){
            for(int j = i - 1; j >= rank; j--){
                arr[j + 1] = arr[j];
            }
        }

        arr[rank] = i;
    }

    vector<int> ans(101, 0);
    for(int i = 1; i <= M; i++){
        int rank;
        cin >> rank;

        int cur = arr[M - i + 1];
        if(ans[rank] != 0 && i > 1){
            for(int j = i - 1; j >= rank; j--){
                ans[j + 1] = ans[j];
            }
        }

        ans[rank] = cur;
    }

    for(int i = 1; i <= 3; i++){
        cout << ans[i] << "\n";
    }

    return 0;
}
```