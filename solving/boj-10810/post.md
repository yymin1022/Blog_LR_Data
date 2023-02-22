[문제 바로가기](https://boj.kr/10810)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> arr;
    for(int i = 0; i <= N; i++){
        arr.push_back(0);
    }

    for(int i = 0; i < M; i++){
        int a, b, c;
        cin >> a >> b >> c;
        for(int j = a; j <= b; j++){
            arr[j] = c;
        }
    }

    for(int i = 1; i <= N; i++){
        cout << arr[i] << " ";
    }

    return 0;
}
```