[문제 바로가기](https://boj.kr/9024)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N, K;
        cin >> N >> K;

        vector<int> num;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            num.push_back(input);
        }

        sort(num.begin(), num.end());

        int cnt = 0;
        int ansSum = 2147483647;
        int fromL = 0;
        int fromR = N - 1;
        while(fromL < fromR){
            int tmpSum = num[fromL] + num[fromR];

            if(abs(tmpSum - K) < abs(ansSum - K)){
                ansSum = tmpSum;
                cnt = 1;
            }else if(abs(tmpSum - K) == abs(ansSum - K)){
                cnt++;
            }

            if(tmpSum > K){
                fromR--;
            }else{
                fromL++;
            }
        }

        cout << cnt << "\n";
    }

    return 0;
}

```
