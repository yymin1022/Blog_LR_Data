[문제 바로가기](https://boj.kr/15645)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[100001][3];
int dp_max[100001][3];
int dp_min[100001][3];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        cin >> arr[i][0] >> arr[i][1] >> arr[i][2];
    }

    dp_max[0][0] = arr[0][0];
    dp_max[0][1] = arr[0][1];
    dp_max[0][2] = arr[0][2];
    dp_min[0][0] = arr[0][0];
    dp_min[0][1] = arr[0][1];
    dp_min[0][2] = arr[0][2];
    for(int i = 1; i < N; i++){
        dp_max[i][0] = max(dp_max[i - 1][0], dp_max[i - 1][1]) + arr[i][0];
        dp_max[i][1] = max(dp_max[i - 1][0], max(dp_max[i - 1][1], dp_max[i - 1][2])) + arr[i][1];
        dp_max[i][2] = max(dp_max[i - 1][1], dp_max[i - 1][2]) + arr[i][2];

        dp_min[i][0] = min(dp_min[i - 1][0], dp_min[i - 1][1]) + arr[i][0];
        dp_min[i][1] = min(dp_min[i - 1][0], min(dp_min[i - 1][1], dp_min[i - 1][2])) + arr[i][1];
        dp_min[i][2] = min(dp_min[i - 1][1], dp_min[i - 1][2]) + arr[i][2];
    }

    cout << max(dp_max[N - 1][0], max(dp_max[N - 1][1], dp_max[N - 1][2])) << " ";
    cout << min(dp_min[N - 1][0], min(dp_min[N - 1][1], dp_min[N - 1][2])) << "\n";

    return 0;
}

```