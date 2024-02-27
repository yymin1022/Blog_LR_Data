[문제 바로가기](https://boj.kr/11497)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        vector<int> arr;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            arr.push_back(input);
        }

        sort(arr.begin(), arr.end());

        int ans = 0;
        for(int i = 2; i < N; i++){
            ans = max(arr[i] - arr[i - 2], ans);
        }

        cout << ans << "\n";
    }

    return 0;
}
```