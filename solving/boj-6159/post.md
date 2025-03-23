[문제 바로가기](https://boj.kr/6159)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, S;
    cin >> N >> S;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    int ans = 0;
    for(int i = 0; i < N - 1; i++){
        for(int j = i + 1; j < N; j++){
            if(arr[i] + arr[j] <= S){
                ans++;
            }else{
                break;
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```