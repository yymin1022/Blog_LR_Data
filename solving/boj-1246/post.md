[문제 바로가기](https://boj.kr/1246)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> arr;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    int ans = 0;
    int idx = 0;
    for(int i = 1; i <= min(N, M); i++){
        if(ans <= i * arr[M - i]){
            ans = i * arr[M - i];
            idx = i;
        }
    }

    cout <<arr[M - idx] << " ";
    cout << ans << "\n";

    return 0;
}
```