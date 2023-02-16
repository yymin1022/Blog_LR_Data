[문제 바로가기](https://boj.kr/10972)

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

    if(next_permutation(arr.begin(), arr.end())){
        for(int i = 0; i < N; i++){
            cout << arr[i] << " ";
        }
    }else{
        cout << -1 << "\n";
    }

    return 0;
}
```