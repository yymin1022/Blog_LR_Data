[문제 바로가기](https://boj.kr/25858)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, D;
    cin >> N >> D;

    int sum = 0;
    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
        sum += input;
    }

    for(int i = 0; i < N; i++){
        cout << D / sum * arr[i] << "\n";
    }

    return 0;
}
```