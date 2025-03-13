[문제 바로가기](https://boj.kr/13458)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int B, C;
    cin >> B >> C;

    long long ans = N;
    for (int i = 0; i < N; i++){
        arr[i] -= B;
        if(arr[i] > 0){
            ans += (arr[i] + C - 1) / C;
        }
    }

    cout << ans << "\n";

    return 0;

```