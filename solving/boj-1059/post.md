[문제 바로가기](https://boj.kr/1059)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int L;
    cin >> L;

    vector<int> arr;
    for(int i = 0; i < L; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int N;
    cin >> N;

    sort(arr.begin(), arr.end());

    for(int i = 0; i <= L; i++){
        if(arr[i] > N) {
            cout << (N - arr[i - 1]) * (arr[i] - N) - 1;
            return 0;
        }else if(arr[i] == N) {
            cout << 0 << "\n";
            return 0;
        }
    }

    return 0;
}
```