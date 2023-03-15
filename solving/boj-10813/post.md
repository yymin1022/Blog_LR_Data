[문제 바로가기](https://boj.kr/10813)

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
        arr.push_back(i);
    }

    for(int i = 0; i < M; i++){
        int a, b;
        cin >> a >> b;
        int tmp = arr[a];
        arr[a] = arr[b];
        arr[b] = tmp;
    }

    for(int i = 1; i <= N; i++){
        cout << arr[i] << " ";
    }

    return 0;
}
```