[문제 바로가기](https://boj.kr/11441)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr(N, 0);
    for(int i = 1; i <= N; i++){
        cin >> arr[i];
        arr[i] += arr[i - 1];
    }

    int M;
    cin >> M;
    for(int i = 0; i < M; i++){
        int x, y;
        cin >> x >> y;

        cout << arr[y] - arr[x - 1] << "\n";
    }

    return 0;
}```