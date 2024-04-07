[문제 바로가기](https://boj.kr/18114)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, C;
    cin >> N >> C;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);

        if(input == C){
            cout << 1 << "\n";
            return 0;
        }
    }

    for(int i = 0; i < N; i++){
        for(int j = i + 1; j < N; j++){
            if(arr[i] + arr[j] == C){
                cout << 1 << "\n";
                return 0;
            }
        }
    }

    sort(arr.begin(), arr.end());

    for(int i = 0; i < N; i++){
        int fromL = i + 1;
        int fromR = N - 1;
        int sum = arr[i];
        while(fromL < fromR){
            int cur = sum + arr[fromL] + arr[fromR];
            if(cur == C){
                cout << 1 << "\n";
                return 0;
            }
            if(cur < C){
                fromL++;
            }else {
                fromR--;
            }
        }
    }

    cout << 0 << "\n";

    return 0;
}
```