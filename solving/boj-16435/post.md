[문제 바로가기](https://boj.kr/16435)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, L;
    cin >> N >> L;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    for(int i = 0; i < N; i++){
        if(L < arr[i]){
            break;
        }

        L++;
    }

    cout << L << "\n";

    return 0;
}
```