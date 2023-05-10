[문제 바로가기](https://boj.kr/16678)

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
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    long long ans = 0;
    int tmp = 1;
    for(int i = 0; i < N; i++){
        if(arr[i] >= tmp){
            ans += arr[i] - tmp;
            tmp++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```