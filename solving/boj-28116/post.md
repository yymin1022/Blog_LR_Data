[문제 바로가기](https://boj.kr/28116)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[500001];
int cnt[500001];
int idx[500001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        cin >> arr[i];
        idx[arr[i]] = i;
    }

    for(int i = 0; i < N; i++){
        if(arr[i] != i + 1){
            cnt[arr[i] - 1] += abs(idx[i + 1] - i);
            cnt[arr[idx[i + 1]] - 1] += abs(idx[i + 1] - i);

            int tmpArr = arr[i];
            int tmpIdx = idx[arr[i]];
            arr[i] = arr[idx[i + 1]];
            arr[idx[i + 1]] = tmpArr;

            idx[tmpArr] = idx[i + 1];
            idx[i + 1] = tmpIdx;
        }
    }

    for(int i = 0; i < N; i++){
        cout << cnt[i] << " ";
    }

    return 0;
}
```