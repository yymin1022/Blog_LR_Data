[문제 바로가기](https://boj.kr/14921)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> liquid;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        liquid.push_back(input);
    }

    int fromL = 0;
    int fromR = N - 1;
    long long answer = 200000001;
    while(fromL < fromR){
        long long tempSum = liquid[fromL] + liquid[fromR];

        if(abs(tempSum) < abs(answer)){
            answer = tempSum;
        }

        if(tempSum < 0){
            fromL++;
        }else if(tempSum > 0){
            fromR--;
        }else{
            break;
        }
    }

    cout << answer << "\n";

    return 0;
}

```