[문제 바로가기](https://boj.kr/22970)

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

    int ans = 0;
    for(int i = 0; i < N; i++){
        int cnt = 1;
        for(int j = i - 1; j >= 0; j--){
            if(arr[j] < arr[j + 1]){
                cnt++;
            }else{
                break;
            }
        }

        for(int j = i + 1; j < N; j++){
            if(arr[j] < arr[j - 1]){
                cnt++;
            }else{
                break;
            }
        }

        ans = max(cnt, ans);
    }

    cout << ans << "\n";
    
    return 0;
}
```