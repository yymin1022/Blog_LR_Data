[문제 바로가기](https://boj.kr/20438)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isSleep[5003];
int arr[5003];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K, Q, M;
    cin >> N >> K >> Q >> M;

    for(int i = 0; i < K; i++){
        int input;
        cin >> input;
        isSleep[input] = true;
    }

    for(int i = 3; i < N + 3; i++){
        arr[i] = 1;
    }

    for(int i = 0; i < Q; i++){
        int input;
        cin >> input;

        if(isSleep[input]){
            continue;
        }

        int cur = input;
        while(cur < N + 3){
            if(isSleep[cur]){
                cur += input;
                continue;
            }

            arr[cur] = 0;
            cur += input;
        }
    }

    for(int i = 4; i < N + 3; i++){
        arr[i] += arr[i - 1];
    }

    for(int i = 0; i < M; i++){
        int from, to;
        cin >> from >> to;
        cout << arr[to] - arr[from - 1] << "\n";
    }

    return 0;
}
```