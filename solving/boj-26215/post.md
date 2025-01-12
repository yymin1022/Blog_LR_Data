[문제 바로가기](https://boj.kr/26215)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(input > 1440){
            cout << -1 << "\n";
            return 0;
        }

        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    int ans = 0;
    while(true){
        sort(arr.begin(), arr.end());

        if(arr[N - 1] == 0){
            break;
        }

        arr[N - 1]--;
        if(arr[N - 2] != 0){
            arr[N - 2]--;
        }

        ans++;
        if(ans > 1440){
            cout << -1 << "\n";
            return 0;
        }
    }

    cout << ans << "\n";

    return 0;
}

```
