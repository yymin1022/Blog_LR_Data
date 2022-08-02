[문제 바로가기](https://boj.kr/2565)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> electric;
    for(int i = 0; i < N; i++){
        int from, to;
        cin >> from >> to;

        electric.push_back(make_pair(from, to));
    }

    sort(electric.begin(), electric.end());

    vector<int> dp(100, 1);
    for(int i = 1; i < N; i++){
        for(int j = 0; j < i; j++){
            if(electric[j].second < electric[i].second){
                dp[i] = max(dp[i], dp[j] + 1);
            }
        }
    }

    int answer = 0;
    for(int i = 0; i < N; i++){
        answer = max(answer, dp[i]);
    }

    cout << N - answer << "\n";

    return 0;
}```