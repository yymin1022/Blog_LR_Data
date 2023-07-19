[문제 바로가기](https://boj.kr/1758)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
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

    sort(arr.begin(), arr.end(), greater<int>());

    long long tip = 0;
    for(int i = 0; i < N; i++){
        int cur = arr[i] - i;
        if(cur <= 0){
            break;
        }

        tip += cur;
    }

    cout << tip << "\n";

    return 0;
}
```
