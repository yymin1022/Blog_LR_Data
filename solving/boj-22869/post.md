[문제 바로가기](https://boj.kr/22869)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isAble[5001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    isAble[0] = true;
    for(int i = 0; i < N - 1; i++){
        if(isAble[i]){
            for(int j = i + 1; j < N; j++){
                if((j - i) * (abs(arr[i] - arr[j]) + 1) <= K){
                    isAble[j] = true;
                }
            }
        }
    }

    cout << (isAble[N - 1] ? "YES" : "NO") << "\n";

    return 0;
}

```