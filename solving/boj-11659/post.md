[문제 바로가기](https://boj.kr/11659)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    int nums[100001] = {0,};
    for(int i = 1; i <= N; i++){
        cin >> nums[i];
        nums[i] += nums[i - 1];
    }

    for(int k = 0; k < M; k++){
        int i, j;
        cin >> i  >> j;

        cout << nums[j] - nums[i - 1] << "\n";
    }

    return 0;
}```