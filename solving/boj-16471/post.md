[문제 바로가기](https://boj.kr/16471)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[2][100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N * 2; i++){
        cin >> arr[i / N][i % N];
    }

    sort(arr[0], arr[0] + N);
    sort(arr[1], arr[1] + N);

    for(int i = 0; i < N / 2 + 1; i++){
        if(arr[0][i] >= arr[1][i + N / 2]){
            cout << "NO" << "\n";
            return 0;
        }
    }

    cout << "YES" << "\n";

    return 0;
}
```
