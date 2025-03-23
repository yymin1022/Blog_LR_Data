[문제 바로가기](https://boj.kr/4159)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    while(true){
        int N;
        cin >> N;
        if(N == 0){
            break;
        }

        vector<int> arr;
        for (int i = 0; i < N; i++) {
            int input;
            cin >> input;
            arr.push_back(input);
        }

        sort(arr.begin(), arr.end());
        arr.push_back(1422);

        bool flag = true;
        for(int i = 1; i < N; i++){
            if(arr[i] - arr[i - 1] > 200){
                flag = false;
                break;
            }
        }

        if(flag && 1422 - arr[N - 1] > 100){
            flag = false;
        }

        cout << (flag ? "POSSIBLE" : "IMPOSSIBLE") << "\n";
    }

    return 0;
}
```